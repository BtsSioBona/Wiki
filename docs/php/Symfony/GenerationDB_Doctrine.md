 ## Après avoir créé la base de donnée et vérifier le fichier parameters.yml
- On crée la BDD
```bash
php bin/console doctrine:database:create
```
- On génère nos entities :
```bash
 php bin/console doctrine:generate:entity
```
- on génère les gettters & setters
```bash
 php bin/console doctrine:generate:entities AppBundle/Entity/
```
- On crée le schema ( le dump-sql pour avoir le script de création de la db )
```bash
php bin/console doctrine:schema:update --force --dump-sql 
```
- Pour générer les repositories : on Ajoute l'annotation suivante dans les Entity en question
``` php

/**
 * @ORM\Entity(repositoryClass="AppBundle\Repository\ProductRepository")
 */
```

- Et on tape la ligne de commpande suivante pour générer le Dossier Ainsi que tous les Repository

```bash
php bin/console doctrine:generate:entities AppBundle
```


### Exemple d'Entity et Repository générés :
- Entity
```php
<?php
namespace AppBundle\Entity;
use Doctrine\ORM\Mapping as ORM;


/**
 * @ORM\Entity(repositoryClass="AppBundle\Repository\ProducteurRepository")
 */
class Producteur
{
    /**
     * @ORM\Id
     * @ORM\Column(type="integer")
     * @ORM\GeneratedValue(strategy="AUTO")
     */
    private $id;

    /**
     * @ORM\Column(type="integer", nullable=false)
     */
    private $codeProducteur;

    /**
     * @ORM\Column(type="string", nullable=true)
     */
    private $prenom;

    /**
     * @ORM\Column(type="string", nullable=true)
     */
    private $nom;

    /**
     *
     */
    private $adr1;

    /**
     * @ORM\Column(type="string", nullable=true)
     */
    private $adr2;

    /**
     * @ORM\Column(type="string", nullable=true)
     */
    private $cp;

    /**
     * @ORM\Column(type="string", nullable=true)
     */
    private $ville;

    /**
     * @ORM\Column(type="decimal", nullable=true)
     */
    private $distanceFromagerie;

    /**
     * @ORM\ManyToOne(targetEntity="Secteur", inversedBy="producteur")
     * @ORM\JoinColumn(name="secteur_id", referencedColumnName="id", nullable=false)
     *
     */
    private $secteur;

    /**
     * @ORM\OneToMany(targetEntity="Ramassage", mappedBy="producteur")
     */
    private $ramassage;

    /**
     * @ORM\ManyToOne(targetEntity="Ramasseur", inversedBy="producteur")
     * @ORM\JoinColumn(name="ramasseur_id", referencedColumnName="id", nullable=false)
     */
    private $ramasseur;
    /**
     * Constructor
     */
    public function __construct()
    {
        $this->ramassage = new \Doctrine\Common\Collections\ArrayCollection();
    }

    /**
     * Get id
     *
     * @return integer
     */
    public function getId()
    {
        return $this->id;
    }

    /**
     * Set codeProducteur
     *
     * @param integer $codeProducteur
     *
     * @return Producteur
     */
    public function setcodeProducteur($codeProducteur)
    {
        $this->codeProducteur = $codeProducteur;

        return $this;
    }

    /**
     * Get codeProducteur
     *
     * @return integer
     */
    public function getcodeProducteur()
    {
        return $this->codeProducteur;
    }

    /**
     * Set prenom
     *
     * @param string $prenom
     *
     * @return Producteur
     */
    public function setPrenom($prenom)
    {
        $this->prenom = $prenom;

        return $this;
    }

    /**
     * Get prenom
     *
     * @return string
     */
    public function getPrenom()
    {
        return $this->prenom;
    }

    /**
     * Set nom
     *
     * @param string $nom
     *
     * @return Producteur
     */
    public function setNom($nom)
    {
        $this->nom = $nom;

        return $this;
    }

    /**
     * Get nom
     *
     * @return string
     */
    public function getNom()
    {
        return $this->nom;
    }

    /**
     * Set adr2
     *
     * @param string $adr2
     *
     * @return Producteur
     */
    public function setAdr2($adr2)
    {
        $this->adr2 = $adr2;

        return $this;
    }

    /**
     * Get adr2
     *
     * @return string
     */
    public function getAdr2()
    {
        return $this->adr2;
    }

    /**
     * Set cp
     *
     * @param string $cp
     *
     * @return Producteur
     */
    public function setCp($cp)
    {
        $this->cp = $cp;

        return $this;
    }

    /**
     * Get cp
     *
     * @return string
     */
    public function getCp()
    {
        return $this->cp;
    }

    /**
     * Set ville
     *
     * @param string $ville
     *
     * @return Producteur
     */
    public function setVille($ville)
    {
        $this->ville = $ville;

        return $this;
    }

    /**
     * Get ville
     *
     * @return string
     */
    public function getVille()
    {
        return $this->ville;
    }

    /**
     * Set distanceFromagerie
     *
     * @param string $distanceFromagerie
     *
     * @return Producteur
     */
    public function setDistanceFromagerie($distanceFromagerie)
    {
        $this->distanceFromagerie = $distanceFromagerie;

        return $this;
    }

    /**
     * Get distanceFromagerie
     *
     * @return string
     */
    public function getDistanceFromagerie()
    {
        return $this->distanceFromagerie;
    }

    /**
     * Set secteur
     *
     * @param \AppBundle\Entity\Secteur $secteur
     *
     * @return Producteur
     */
    public function setSecteur(\AppBundle\Entity\Secteur $secteur)
    {
        $this->secteur = $secteur;

        return $this;
    }

    /**
     * Get secteur
     *
     * @return \AppBundle\Entity\Secteur
     */
    public function getSecteur()
    {
        return $this->secteur;
    }

    /**
     * Add ramassage
     *
     * @param \AppBundle\Entity\Ramassage $ramassage
     *
     * @return Producteur
     */
    public function addRamassage(\AppBundle\Entity\Ramassage $ramassage)
    {
        $this->ramassage[] = $ramassage;

        return $this;
    }

    /**
     * Remove ramassage
     *
     * @param \AppBundle\Entity\Ramassage $ramassage
     */
    public function removeRamassage(\AppBundle\Entity\Ramassage $ramassage)
    {
        $this->ramassage->removeElement($ramassage);
    }

    /**
     * Get ramassage
     *
     * @return \Doctrine\Common\Collections\Collection
     */
    public function getRamassage()
    {
        return $this->ramassage;
    }

    /**
     * Set ramasseur
     *
     * @param \AppBundle\Entity\Ramasseur $ramasseur
     *
     * @return Producteur
     */
    public function setRamasseur(\AppBundle\Entity\Ramasseur $ramasseur)
    {
        $this->ramasseur = $ramasseur;

        return $this;
    }

    /**
     * Get ramasseur
     *
     * @return \AppBundle\Entity\Ramasseur
     */
    public function getRamasseur()
    {
        return $this->ramasseur;
    }
}
```
- Repository
```php
<?php

namespace AppBundle\Repository;

/**
 * ProducteurRepository
 *
 * This class was generated by the Doctrine ORM. Add your own custom
 * repository methods below.
 */
class ProducteurRepository extends \Doctrine\ORM\EntityRepository
{
}
```
