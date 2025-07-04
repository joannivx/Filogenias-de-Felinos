#Filogenias de Felinos

![text](https://wallpapers.com/images/hd/panther-1920-x-1200-background-8az3ygd3x7le6rvm.jpg)

##Nombre del Proyecto: 
- Filogenia de Felinos basada en el gen SERPINA3
##Autor
- Melissa Joan Dueñas Cano 
##Propósito del programa
- Generar un árbol filogenético a partir de secuencias del gen SERPINA3 en especies de la familia Felidae. Está diseñado para funcionar en el entorno Hoffman y puede ser utilizado para entender relaciones evolutivas entre felinos con base en un solo gen.
- Usamos NCBI Gene o NCBI Nucleotide, específicamente buscando secuencias del gen SERPINA3 en especies de la familia Felidae.
- Descarga solo secuencias en formato FASTA
- Alinear las secuencias con muscle
- Instala IQ-TREE
- Usar mesquite y Fig tree para ver la filogénia

##SCRIPT

- como obtener los genes de ncbi
./datasets download gene symbol SERPINA3 -- orthologs Felidae -- filename SERPINA3_Felidae.zip

./datasets summary gene symbol SERPINA3 -- orthologs Felidae -- as -Json-lines ./dataform □| sv gene -- fields tax-name$
- Bajar genes de una lista
./datasets download gene SERPINA3-id -- input file Gene.SA.CATS.txt -- filename SA.CATS.zip

- Descomprimir un archivo
unzip  SERPINA3_Felidae.zip

- ir a la carpeta datasets
module load iqtree/2.2.2.6
iqtree2
istree2 -s muscle_rna_fna

-Como bajar un citocromo
./muscle3.8.linux -in rna.fna -out muscle_rna_fna - maxiters t- diags

- Descargar del Supercomputador desde gitbash
scp dechavez@hoffman2.idre.ucla.edu:(pwd) rna.fna

-Subir el archivo descargado a el programa mesquite y Figtree 

#Lo que debe tener cada carpeta:
- Data
  rna.fna (archivo FASTA descargado de NCBI)
  muscle_rna_fna.fasta (alineamiento generado por MUSCLE)
- Scripts (arriba)
- Results Serpina3_Felidae.treefile (vizualización en mesquite y figtree)
  



  
