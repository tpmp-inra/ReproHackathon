# Ce dossier contient les résultats du [ReproHackathon2](../docs/hackathon_2_programme.md)

## Organisation proposée

* Un sous-répertoire par groupe
* Associé à une branche
* Incluant la description
  * des matériels et méthodes utilisés
  * de l'avancement au fur et à mesure
  * un bilan des réalisations en fin de hackathon

## Exemples de lignes de commandes:

* FastTree:
  - Container: `evolbioinfo/fasttree:v2.1.9`
  - Command:
```
	FastTree -nt -gtr -gamma -spr 4 -mlacc 2 -slownni <align.fa> > <output.nhx>
```

* RAxML:

    - Container: `evolbioinfo/raxml:v8.2.0-avx2`
    - Command:    
```
raxmlHPC -T <cpus> -p 1 -m GTRGAMMA --no-bfgs -s <align.phy> -n NAME
	mv RAxML_bestTree.NAME raxmloutput.nhx
```

* IQTree:
    - Container: `evolbioinfo/iqtree:v1.4.2`
    - Command:
```
iqtree -m GTR+G4 -s <align.fa> -seed 1 -nt <cpus>
mv <align.fa>.treefile iqtreeoutput.nhx
```

* PhyML:
    - Container: `evolbioinfo/phyml:v3.3.20180129`
    - Command:
```
phyml -i <align.phy> --r_seed 1 -d nt -b 0 -m GTR -f e -c 4 -a e -s SPR --n_rand_starts 1 -o tlr -p --run_id ID
mv *_phyml_tree_ID.txt outputphyml.nhx
```


* Comparer 2 arbres: [gotree](https://github.com/fredericlemoine/gotree)
    - Container: `evolbioinfo/gotree:v0.2.10`
    - Command:
```
gotree compare trees --binary -i <arbre1> -c <arbre2>
```

* Reformater `fasta <=> phylip`: [goalign](https://github.com/fredericlemoine/goalign)
    - Container: `evolbioinfo/goalign:v0.2.9`
    - Commands:
```
# phylip => fasta
goalign reformat fasta -i <align.phy> -p -o align.fa
# fasta => phylip
goalign reformat phylip -i <align.fa> -o align.phy
```

## Participants/Groupes :


## Liens utiles

* Article: [Zhou MBE 2018](https://academic.oup.com/mbe/article/35/2/486/4644721)
* Images Docker utiles: [evolbioinfo](https://hub.docker.com/r/evolbioinfo/)
* Données de l'article: [FigShare](https://figshare.com/projects/Evaluating_fast_maximum_likelihood-based_phylogenetic_programs_using_empirical_phylogenomic_data_sets/22040)
* Appliances disponibles dans Biosphère : [catalogue RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) 
  * [BioPipes](https://biosphere.france-bioinformatique.fr/catalogue/appliance/119) : Nextflow, SnakeMake, Conda configuré avec Bioconda, Docker and Compose 
  * [Ubuntu-16.04](https://biosphere.france-bioinformatique.fr/catalogue/appliance/88), [Ubuntu-Desktop](https://biosphere.france-bioinformatique.fr/catalogue/appliance/118) : Docker, Ansible, Bioconda, Desktop MATE
  * [cluster SLURM](https://biosphere.france-bioinformatique.fr/catalogue/appliance/102)
  * [cluster SGE](https://biosphere.france-bioinformatique.fr/catalogue/appliance/69)

## Quelques commandes utiles
