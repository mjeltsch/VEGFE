# VEGFE

## Phylogenetic analysis of VEGF-Es

### System requirements

The workflow was tested (and will likely work) only on Ubuntu Linux 18.04 or 20.04. Requirements are:

t_coffee, PhyML and the ETE3 toolkit. The script uses some functions from phylolib.py, and this library might require the installation of a few other python modules, which can be done via the pip3 package manager.

### Description of the workflow

A Psiblast limited to the taxon Viridae (taxid:10239) was run against the starting sequence AAD03735.1 (vascular endothelial growth factor homolog VEGF-E from Orf virus) until no new sequences were found above the 0.005 threshold. The Fasta descriptions were adjusted to include virus name abbreviations and host species.

For each of the 13 identified host species, the VEGF-A165, PlGF-1 and VEGF-B186 orthologs were retrieved if available and included in the alignment and tree building. Only three out of the eight fish VEGF-B sequences were available. Therefore, we included both zebrafish VEGFB sequences is the analyisis. Similarly, no VEGF sequences were available for Halichoerus grypus (grey seal). These were replaced with sequences from the closest species for which VEGF sequences were available (Zalophus californianus, California sea lion).
The protein sequence alignment was performed with m_coffee 13.41.0.28bdc39, the tree building with PhyML 3.3.3:3.3.20170530+dfsg-2 and the visualization of the tree with the ETE Toolkit 3.0.0b34. The workflow and all sequences used for the analysis are available from github.

The non-viral VEGF sequences were retreived using NCBI pblast with query sequences human VEGF-A165 (P15692-4), PlGF-2 (P49763-3) and VEGF-B186 (P49765) with max results = 500. This results in ~351 for VEGF-A165, ~364 for PlGF-1, and 379 for VEGF-B186. The best hit for each host species/VEGF combination was include in the alignment and tree building. The tree was visualized with ete3 using the outgroup P01128.1 to root the tree (v-sis, PDGF-related-transforming protein sis).

* >sp|P15692-4|VEGFA_HUMAN Isoform VEGF165 of Vascular endothelial growth factor A OS=Homo sapiens OX=9606 GN=VEGFA
MNFLLSWVHWSLALLLYLHHAKWSQAAPMAEGGGQNHHEVVKFMDVYQRSYCHPIETLVD
IFQEYPDEIEYIFKPSCVPLMRCGGCCNDEGLECVPTEESNITMQIMRIKPHQGQHIGEM
SFLQHNKCECRPKKDRARQENPCGPCSERRKHLFVQDPQTCKCSCKNTDSRCKARQLELN
ERTCRCDKPRR

* >sp|P49763-2|PLGF_HUMAN Isoform PlGF-1 of Placenta growth factor OS=Homo sapiens OX=9606 GN=PGF
MPVMRLFPCFLQLLAGLALPAVPPQQWALSAGNGSSEVEVVPFQEVWGRSYCRALERLVD
VVSEYPSEVEHMFSPSCVSLLRCTGCCGDENLHCVPVETANVTMQLLKIRSGDRPSYVEL
TFSQHVRCECRPLREKMKPERCGDAVPRR

* >sp|P49765|VEGFB_HUMAN Vascular endothelial growth factor B OS=Homo sapiens OX=9606 GN=VEGFB PE=1 SV=2
MSPLLRRLLLAALLQLAPAQAPVSQPDAPGHQRKVVSWIDVYTRATCQPREVVVPLTVEL
MGTVAKQLVPSCVTVQRCGGCCPDDGLECVPTGQHQVRMQILMIRYPSSQLGEMSLEEHS
QCECRPKKKDSAVKPDRAATPHHRPQPRSVPGWDSAPGAPSPADITHPTPAPGPSAHAAP
STTSALTPGPAAAAADAAASSVAKGGA

13 host species (6 mammals, 7 fish):

* Ovis aries
* Capra hircus
* Homo sapiens
* Bos taurus
* Cervus elaphus
* Zalophus californianus

* Lates calcarifer
* Epinephelus coioides
* Seriola dumerili
* Scophthalmus maximus
* Cyprinus carpio
* Neolamprologus brichardi
* Sphaeramia orbicularis
