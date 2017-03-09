## L'erreur : No Metadata Classes to process.

- Après la commande
```
php bin/console doctrine:schema:update --force
```
- L'erreur ci dessous peut apparaitre
```
No Metadata Classes to process.
```
## fix : Il manque le Namespace dans les Entity à ajouter.

Exemple : 

```php
<?php
namespace AppBundle\Entity;
use Doctrine\ORM\Mapping as ORM;

/**
* @ORM\Entity(repositoryClass="AppBundle\Repository\SecteurRepository")
 */
class Secteur
{
    /**
     * @ORM\Id
     * @ORM\Column(type="integer")
     * @ORM\GeneratedValue(strategy="AUTO")
     */
    private $id;

    /**
     * @ORM\Column(type="integer", unique=true, nullable=false)
     */
    private $codeSecteur;

    /**
     * @ORM\Column(type="string", nullable=true)
     */
    private $libelle;

    /**
     * @ORM\OneToMany(targetEntity="Ramasseur", mappedBy="secteur")
     */
    private $ramasseur;

    /**
     * @ORM\OneToMany(targetEntity="Producteur", mappedBy="secteur")
     *
     *
     */
    private $producteur;
    /**
     * Constructor
     */
    public function __construct()
    {
        $this->ramasseur = new \Doctrine\Common\Collections\ArrayCollection();
        $this->producteur = new \Doctrine\Common\Collections\ArrayCollection();
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
     * Set codeSecteur
     *
     * @param integer $codeSecteur
     *
     * @return Secteur
     */
    public function setCodeSecteur($codeSecteur)
    {
        $this->codeSecteur = $codeSecteur;

        return $this;
    }

    /**
     * Get codeSecteur
     *
     * @return integer
     */
    public function getCodeSecteur()
    {
        return $this->codeSecteur;
    }

    /**
     * Set libelle
     *
     * @param string $libelle
     *
     * @return Secteur
     */
    public function setLibelle($libelle)
    {
        $this->libelle = $libelle;

        return $this;
    }

    /**
     * Get libelle
     *
     * @return string
     */
    public function getLibelle()
    {
        return $this->libelle;
    }

    /**
     * Add ramasseur
     *
     * @param \AppBundle\Entity\Ramasseur $ramasseur
     *
     * @return Secteur
     */
    public function addRamasseur(\AppBundle\Entity\Ramasseur $ramasseur)
    {
        $this->ramasseur[] = $ramasseur;

        return $this;
    }

    /**
     * Remove ramasseur
     *
     * @param \AppBundle\Entity\Ramasseur $ramasseur
     */
    public function removeRamasseur(\AppBundle\Entity\Ramasseur $ramasseur)
    {
        $this->ramasseur->removeElement($ramasseur);
    }

    /**
     * Get ramasseur
     *
     * @return \Doctrine\Common\Collections\Collection
     */
    public function getRamasseur()
    {
        return $this->ramasseur;
    }

    /**
     * Add producteur
     *
     * @param \AppBundle\Entity\Producteur $producteur
     *
     * @return Secteur
     */
    public function addProducteur(\AppBundle\Entity\Producteur $producteur)
    {
        $this->producteur[] = $producteur;

        return $this;
    }

    /**
     * Remove producteur
     *
     * @param \AppBundle\Entity\Producteur $producteur
     */
    public function removeProducteur(\AppBundle\Entity\Producteur $producteur)
    {
        $this->producteur->removeElement($producteur);
    }

    /**
     * Get producteur
     *
     * @return \Doctrine\Common\Collections\Collection
     */
    public function getProducteur()
    {
        return $this->producteur;
    }
}

```
