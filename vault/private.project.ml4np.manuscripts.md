---
id: ea4bb630-7e79-482c-aaae-df6e6763039d
title: Manuscripts
desc: publication(s) resulting from the project
updated: 1600784773013
created: 1600784773013
stub: false
---

### Gdocs [[gdocs link](https://docs.google.com/document/d/1cHPtgKpp_IvhFsHPU0aKdnVd-mh_WfRWaGDoDgQ-ypk/edit#)]

### Latex version

\documentclass[notitlepage]{revtex4-1}

\usepackage{amsmath}

\usepackage{bm}

\usepackage{physics}

\usepackage{algorithm}
\usepackage{algpseudocode}

\usepackage{graphicx}
\usepackage{subcaption}
\usepackage{epstopdf}
\usepackage[maxbibnames=20,maxcitenames=20,backend=biber,style=chem-acs,biblabel=brackets,articletitle=true]{biblatex}
\addbibresource{ref.bib}

\graphicspath{{img/}}

\everymath{\displaystyle}

\begin{document}

\begin{titlepage}

\newcommand{\HRule}{\rule{\linewidth}{0.5mm}} % Defines a new command for the horizontal lines, change thickness here

\center % Center everything on the page
 
%----------------------------------------------------------------------------------------
%	HEADING SECTIONS
%----------------------------------------------------------------------------------------

\textsc{\LARGE Sorbonne Université}\\[1.5cm] % Name of your university/college
\textsc{\Large Master de Physique des systèmes complexes}\\[0.5cm] % Major heading such as course name
\textsc{\large Proposition de projet}\\[0.5cm] % Minor heading such as course title

%----------------------------------------------------------------------------------------
%	TITLE SECTION
%----------------------------------------------------------------------------------------

\HRule \\[0.4cm]
{ \huge \bfseries Machine Learning for Natural Products : A Statistical Physics Approach }\\[0.4cm] % Title of your document
\HRule \\[1.5cm]
 
%----------------------------------------------------------------------------------------
%	AUTHOR SECTION
%----------------------------------------------------------------------------------------

\begin{minipage}{0.8\textwidth}
\begin{flushleft} \large
\emph{Author:}\\
Moncef \textsc{Belguechi} Pierre-Marie \textsc{Allard}% Your name
\end{flushleft}
\end{minipage}
~
\begin{minipage}{0.4\textwidth}
\begin{flushright} \large
\end{flushright}
\end{minipage}\\[2cm]

% If you don't want a supervisor, uncomment the two lines below and remove the section above
%\Large \emph{Author:}\\
%John \textsc{Smith}\\[3cm] % Your name

%----------------------------------------------------------------------------------------
%	DATE SECTION
%----------------------------------------------------------------------------------------

{\large Spring 2020}\\[2cm] % Date, change the \today to a set date if you want to be precise

%----------------------------------------------------------------------------------------
%	LOGO SECTION
%----------------------------------------------------------------------------------------

\includegraphics[width=0.4 \linewidth]{SUlogo.jpg}\\ [1cm] % Include a department/university logo - this will require the graphicx package
 
%----------------------------------------------------------------------------------------

\vfill % Fill the rest of the page with whitespace

\end{titlepage}


\title{Bioactive natural products exploration through Deep Learning}

\author{Moncef Belguechi,Pierre-Marie Allard}

\email{moncef.belguechi@gmail.com}
\affiliation{Sorbonne Université - Faculté des Sciences, 4 rue Jussieu, 75005, Paris, France,
School of Pharmaceutical Sciences, EPGL, University of Geneva,
University of Lausanne, Quai Ernest-Ansermet 30, CH-1211 Geneva 4, Switzerland} 


\begin{abstract}
The outbreak of Covid-19 caused by the coronavirus COV-2 has shown how the spread of epidemic diseases can be considerably accelerated by easy access to transport. This phenomenon is not new and the risks engaged by the "modern world"'s habits have been largely pointed out by the scientific community \cite{Blamont}. In the context of the pandemia that we are experiencing, an editorial in Nature Plants suggests that a better understanding of plants could slow down epidemic diseases among many other benefits of the use of plants \cite{natureplants}. 
This exploratory work might be relevant for this purpose. Part of a drug discovery effort, this project aims to harness the chemo-diversity of a large collection of natural products by finding a standard computer method capable to exploit mass spectrometry data. Recently, it has been shown that Restrictive Boltzmann Machine (RBM) can be trained to learn complex high-dimensional data for statistical analysis of protein sequences \cite{Tubiana2018}. Grounded to the statistical physics framework, this machine learning algorithm presents the advantage of having a good trade-off efficiency and interpretability. As any data science project, the main challenge remains on the preparation of the data to be usable by machine learning algorithms such as RBMs, we present in this report the many elements that need to be considered in order to be able to successfully use our neural network. The goals of our statistical analysis are  \textit{organizing spectral data} (as spectral networks for example) \cite{Wang_2016} \textit{annotating spectral data} (for example by linking a structure to a spectra)\cite{Allard2016} and \textit{visualizing relationships between} metabolites (and group of metabolites) and plants.
\end{abstract}

\begin{figure}
  \centering
  \includegraphics[scale=0.3]{Plantextract.jpg}
  
  \label{fig:rbm}
\end{figure}

\maketitle





\section{Introduction and motivations}
Since ancient times, plants have been central for humans all around the world. Natural products have been used for many purposes but one of the most important use has been related to healthcare and the cure of diseases. Medicinal plants are at the core of the history of medicine. The use, combination, and mastery of plants have been experienced by every civilization. Veda texts from Indian civilization date from the second millenary BC, the Ebers Papyrus from the XVI century BC, those text are relevant testimonials of the high interest of plants and their benefits. 
Traditional medicines are based on the results of holistic experimentation but modern medicine has mainly taken the reductionist paradigm for the last 200 years when it comes to the therapeutical object. Indeed, studying natural products for the research of therapeutic bioactivity consisted of studying complex natural extracts and characterizing the main active ingredients of plants or any other natural product. This method, known as Bioactivity-guided fractionation (BGF) has contributed to the synthesis of half of the modern pharmacopeia, however this technique deny the chemical complexity of NP extract in terms of interaction and quantity of metabolites \cite{allard_pharmacognosy}  . To name but one example, the acetylsalicylic acid, also know as aspirin has been synthesized from salicylate that is found in natural products such as the Willow tree. Interestingly, salicylate has been mention as an active ingredient in ancient Sumer clay tablets and Hippocrates mentions it as an efficient compound to reduce fever. Salicylate is an active metabolite part of specific metabolites, small molecules produced by plants, fungi, or bacterias. In one plant extract only, one could find hundreds up to thousands of metabolites, the presence of such a chemo-diversity make plants complex systems.
The motivation for this work lies in the will to study the plant as a complex system instead to focus only on the main active ingredient as it is mainly done in pharmacology. Recent advances in computer science and our ability to process large amounts of data may be opportunities to explore the hollistic paradigm found in traditional medicine. 
In light of the health crisis we are experiencing, a well-known plant has once again attracted the attention of researchers. Indeed, artemisia, a plant used in Chinese pharmacopoeia for several millennia, is known for its anti-malarial activity thanks to one of its active ingredients, artemisin. This plant also seems to have beneficial effects in reducing the viral presence of Covid-19 in affected patients. However, a group of researchers from Free University of Berlin and the Max Planck institute of Colloids and Interfaces  found that pure artemisin did not show much antiviral activity ,instead it is the collection of active small molecules of artemisia that provide better antiviral results against Covid-19, in other words, the whole plant was able to obtain better results against the new coronavirus than its isolated main active ingredient, artemisin \cite{artemisia}. Perhaps this example illustrates the interest of studying natural products as complex systems. Given the amount of data involved in this work, the tools of statistical physics seem relevant to address this issue. 
\vfill

\begin{figure}[h]
  \centering
  \includegraphics[scale=0.2]{chemicalspace.png}
  \caption{Schematic view of the gap between molecular space and reference libraries : The metabolomics community has historically fallen short to annotate new small molecules because of the limited size of Chemical reference libraries to match with the spectrums provided by experimental data. Typically, those libraries con.   }
  
  \label{fig:virt}
\end{figure}

\section*{The chemical space}

Enumeration of the chemical space has been an active topic especially with the rise of computer capacity. In the last section, we define specific metabolites as small molecules responsible for the defense of plants, some of those molecules present bioactive interest as discussed and the topic of this project relies on finding new strategies to characterize, identify and annotate metabolites present in NP extracts. 
The known chemical space gathered in public databases and corporate libraries represents approximately 100 million molecules \cite{chemicalspace}. 
Despite this impressive number, we are lacking information about the structure and the properties of most molecules. 
Chemical reference libraries ( e.g mass spectra, collision cross-section) represent \textless1\% of known molecules. 
This situation could be compared with space observation at Galileo’s times, back 400 years ago: It was possible to have an estimation of the number of stars observable without having them precisely characterized. 
Techniques such as high-resolution fragmentation mass spectrometry have made possible the detection of small molecules ( m/z, intensity, retention time) in complex samples leading to the enumeration of the known chemical space. However, identifying those molecules requires the comparison of the experimental data to corresponding reference values in the libraries to match a molecule. Giving the gap between the known chemical space and chemical reference libraries, it is elusive to imagine identifying small molecules only by comparison of the spectrum and reference dataset, this issue is a well-known limitation in the metabolomics community. Our goal is to find a machine learning strategy that could help annotating unknown metabolites directly from experimental data in an unambiguous manner. Several efforts have started to emerge in the metabolomic community to use machine learning methods \cite{darkchem}\cite{Canopus}. We would like to explore the possibilities to use RBMs because of there specificities compared to other types of Neural Networks (NN), the characteristics of our NN will be presented in the Method section.



\vfill



\section*{Metabolomic}
The Increase of metabolite data obtained by mass spectrometry of plant extracts open unprecedented possibilities to harness the chemo-diversity of large collection of natural product (NP) extracts. Specific metabolite are small molecules produced by bacteria, fungi or plants, those organic compounds are not involved in the growth of an organism like primary metabolites but they play a key role in inter-species defenses.
Humans have been using them as therapeutics, flavourings or pigments for millenaries.    
In this work, we would like to improve the capacity of the metabolomic community to identify and annotate specific metabolite. Our topic, that one could include into a meta-discipline devoted to natural biomedical activity of NP aims to take advantage of the possibilites that machine learning brings to annotate spectral data and link it with chemical structures.   
This apparent complexity is not surprising considering that one could find hundreds up to thousands of metabolites in one plant extract only : Studying plant at the molecular level is studying a complex system.

 The quantity of data coming from mass spectrometry is massive but not yet exploited at it's full potential. This issue is due to the difficulty of annotation of small molecules regarding that chemical references libraries represent barely 1\% of known molecules which limit the possibilities of identification of new compounds coming from experimental data. 
 Historically such holistic approach has been overlooked as the main paradigm has been the reductionist approach for 200 years.
 However, associating the activity of a plant to a single molecule deny the complex interactions of thousands of small molecules that can be found in one extract\cite{allard_pharmacognosy}. The use of computational tools and statistical physics framework could be beneficial to tackle such complex matrices.
 Entering to the high-dimensional world, it might be possible to use statistical analyses to address those questions. 
 
\begin{figure}
  \centering
  \includegraphics[scale=0.3]{plant meta.png}
  \caption{Specific metabolites play a key role for inter-species defenses : they have been used extensively by human beings for thousands of years, to name a few of the most famous ones : Caffeine, Taxol, Artemisin, Morphine, Codeine, Revsveratrol, Cocaine, Quinine, Nicotine...}
  \label{fig:virt}
\end{figure}

\section*{Machine Learning Problematic}

Machine learning approaches in drug discovery are usually run on set of structures \cite{Stokes2020,Tubiana2018}. The training set being in these cases constituted by pairs of structures and bioactivity.
This is perfectly valid and adapted to mine chemical libraries. However the big difference in our case is that we don't have pure chemicals but mixture of thousands to ten of thousands of metabolite per extracts. The second problem is that the annotation step (linking a spectra with a molecule) is a complicated one and that confidence in the annotation is hard to evaluate.
It might thus be interesting to directly exploit spectra, which can be taken as direct structures reflection. Exploiting spectra means relying in experimental data only and also means Independence regarding the metabolite annotation stage. \textit{Exploration of directly the links between spectra ensembles and sought-after bioactivity could thus be an interesting option.}

Another interesting field to investigate would be to establish a computational framework for the implementation of a virtuous cycle of metabolite annotation, such as we previously proposed. \cite{Allard2017a} Here machine learning could be used at the in silico fragmentation stage, trained on pairs of spectra and structure. Machine learning could also be used at the in silico fragmentation stage, notably to infer biosynthetic reaction rules from set of closely related chemicals.

Interesting approaches allowing to predict substructures and associate them to fragmentation spectra have been devised recently and could be implemented and improved. \cite{Rogers2019}


\begin{figure}
  \centering
  \includegraphics[scale=0.6]{Fig_2_rev.pdf}
  \caption{\copyright \textbf{Allard2016} A strategy to generate plausible structures from in-silico databases and annotates new metabolites from experimental data thanks to the extension of the in-silico library. }
  
  \label{fig:virt}
\end{figure}


\section*{Data set}

We have several data-sets gathering various type of information corresponding to 1600 plant extracts.
\begin{itemize}
   
 \item The mass spectrometric data MS1 is a flat file (csv) of 64001 rows and 1600 columns (the plant extracts that we will call samples hereafter). This dataset has three dimensions, mass over charge ratio (m/z) at retention time(RT) on the rows, our features, and the intensity of a feature for each sample. 
 Each feature has an associated fragmentation mass spectra, the purpose of the fragmentation mass spectra is to characterize more specifically the molecule in order to give to each molecule a "fingerprint" of its structure. 
 \item Those informations are gathered in a second dataset, mass spectrometric data MS2 which is a flat file (.mgf) constituted of 64001 blocks. Each block has a header containing parent ion mass, retention time and features identity corresponding to the 64001 rows of our first dataset. 
 \item The third dataset correspond to metadata files for the 1600 samples gathered as a flat file (.csv) and indicating metadata such as botanical characteristic(species,genus,families) and bioactivities against a specific target.
 \item The fourth dataset gather the metadata of the 64001 features on a flat file (.csv) by giving the chemical structures and chemical classes of each feature.
 \item Finally there is a molecular network dataset made by the computation of a pairwise cosine between each spectral features of the second dataset.
 \end{itemize}
 
  \begin{figure}{h}
  \centering
  \includegraphics[scale=0.3]{Tubiana.png}
  \caption{\copyright \textbf{Tubiana2019} Modeling of proteins with RBM : The data used on the visible layer of the network where protein sequences shaped with the Multiple-Sequence Alignment tool,as they are strings, NLP tools were usable to evaluate the occurancy of amino acids in the sequences provided. We need to find a method to encode our spectrums to put them as our input in RBMs. }
  
  \label{fig:rbm}
\end{figure}
 
 \subsection{Discussion}
 
 The datasets we have are not usable in their current state. In order to be able to exploit data, the first step of a machine learning project is called data mining or features engineering. This step consists in preparing the data to be exploitable by the different machine learning techniques. In our case, we are in possession of spectral data consisting of a list of triplets: \textbf{m/z}, \textbf{retention time} and \textbf{intensity}. 
By discretizing the spectrum into several intervals, this representation resembles a model from the natural language processing (NLP): \textit{Bag of Words}. The first two indices could correspond to a word and the intensity to the number of times the word appears in the text. 
Later, we could transform the \textit{Bag of Words}  representation by \textit{One hot encoding}: We replace the list by a matrix such as $M_{kl} = \sum_i \delta_{k_i, k} \delta_{l_i, l} I_i$
Finally, we transform this matrix into a vector, we iterate the procedure for each spectrum and the alignment of the vectors obtained gives a matrix usable with the same type of pipeline as in word processing. 
Several approaches grounded to NLP have been tackled to annotate mass spectrums of metabolites and seems to give interesting results compare to standard techniques to evaluate spectrums, known as similarity measures such as \textit{cosine score}, thoses techniques have good results for identical spectrums but underperform for complex samples \cite{spec2vec}\cite{Mass2motifs}. Nevertheless,we are still lacking of a clear vision on what technique to use. Techniques from NLP seems promising but the  question remaining is what to do whith the output resulting of this kind of method. At the end of the day, we would like to get insights of molecular structures from raw spectra data. This means that we want to move from the space of spectra to the space of structures. We, therefore, need to take into account the different granularity involved in our project to keep close the big picture of our motivations.

\subsubsection{Granularity}

Bearing in mind that one of our objectives is to extract information related to the bioactivities of non-annotated metabolites directly from experimental data, the notion of granularity needs to be addressed. We have just presented the first space, that of the spectra, this space is the lowest level space to make an analogy with computer science, it is the space that contains the raw information on the fingerprint and therefore the existence of a certain quantity of metabolites per spectrum. As we have seen, we first try to link these spectra to molecular structures. We are therefore looking for a technique to be able to move from the space of spectrums to the space of structures. Later, the objective would be to move from the space of structures to the space of bio-activities and this step could even be divided by including the space of taxonomies in order to refine our method.
In doing so, it appears that the molecular object holds a central place in the framework of our problem. In order to be able to perform our statistical analysis, we need to be able to manipulate an object suitable for machine learning techniques. 

\subsection{The molecular object}

Our postulate comes from the fact that machine learning can be used to leverage the identification  of new molecules with interesting bioactivity for humans as it is more and more done \cite{Antibiotic}. Classical methods that consist in searching for a molecule in a library suffer from the size of reference libraries as we have seen: If an unknown molecule is detected and is not present in any of the libraries, the search will not yield anything.
In doing so, starting from the space of the spectrums, we should be able to use a molecular representation that would allow the use of our algorithms.
There are several techniques that encode the structure of a molecule however it appears that SMILES strings represent the state of the art for encoding a molecular representation. 
SMILES (Simplified Molecular Input Line Entry Specification) are sequences of characters. This text format allows the use of NLP tools\cite{hernandez}. This approach seems to be the most interesting, especially since it allows us to continue the analogy with the method we have mentioned, which uses character sequences to encode the structure of proteins.
In addition, it would allow the use of data from large libraries of molecules such as \textbf{PubChem}  or \textbf{HMDB} that provide a SMILES version of their molecules. Despite of the interest of this representation, many different SMILES strings can represent the same molecule, there is a lack of invariance to atom ordering. This limitation needs to be overcome to be able to use this representation in an unambiguous manner.

\begin{figure}
  \centering
  \begin{subfigure}{.35\linewidth}
    \includegraphics[width=\linewidth]{spaces.png}
    \caption{.}
    \label{fig:data}
  \end{subfigure}
  \begin{subfigure}{.35\linewidth}
    \includegraphics[width=\linewidth]{rbmspace.png}
    \caption{ }
    \label{fig:rotdata}
  \end{subfigure}
  \begin{subfigure}{.35\linewidth}
    \includegraphics[width=\linewidth]{SMILES.png}
    \caption{ }
    \label{fig:rotdata}
  \end{subfigure}
  
\caption{To identify and characterise new molecules we need to pass through different spaces. One strategy could be to stack several RBMs to be able to pass from the different representations. For that purpose we need to encode the molecular object as it is shown for the SMILES technique.}
\end{figure}



 



 
 \newpage
 
\begin{figure}{h}
  \centering
  \includegraphics[scale=0.6]{Linear Regression.png}
  \caption{Linear regression over random variables. The orange curve represent the function y that fits the data. The green curve is our regression performed by the function $\hat{y}$. We can see that both functions have a similar behaviour with a reasonable low distance between them indicating that the learning procedure has performed well.  }
  \label{fig:virt}
\end{figure}

\section*{Method}

\subsection*{Machine Learning}

If we wanted to summarize Machine Learning in a nutshell or in one expression , we could say that it consists of learning a function that maps input variables (X) to output variables (Y): 
$$\ Y=F(X) \ $$ 

The task of the algorithm ,in a general manner,is to estimate the function Y by a function $\hat{Y}$. The function $\hat{Y}$ is calculated to perform a prediction of the function Y and to measure the score of our model, we can track its performance with a cost function, the idea of such functions is simply to measure the difference between the predicted value and the actual value. 
The Mean Squarer Error (MSE) is one of the most common cost functions, it is widely  use in Linear Regression : 
\( \mathrm{MSE}=\frac{1}{m} \sum_{i=1}^{m}\left\|\hat{y}^{(i)}-y^{(i)}\right\|^{2} \)

Our goal is to get a score for our MSE function as close as possible to zero (Meaning having the minimum distance between the two functions). Achieving that would mean that our model fit well our data and is able to perform a good prediction. 

Those elements are general aspects that we find in every machine learning models. The idea is to give a first flavour of the domain, for further details about machine learning theory, \textit{The Elements of Statistical Learning} is a very complete reference. In the next section we will focus on the theory of the model we would like to implement for our problematic. 

\newpage


 \subsection*{RBM and Energy Based Model}
 
  Recently, it has been shown that RBM are particularly efficient to learn complex high-dimensional data \cite{Tubiana2018}. In this work, we would like to adapt this method in order to infer spectral features which could be signatures of sought-after bioactive metabolites. RBM constitute a versatile tool that could help to organize spectral data and prioritize them. 
 
 In the dense landscape of machine learning,  RBM are energy-based models (EBM) with generative properties.They can be used in the framework of Deep Learning and have been performing well for tasks such as denoising, recommendation systems and artificial data generation \cite{hinton}. 
 The main idea of EBM is to represent our configuration of data and features as one energy function. The model learn by minimizing this energy function as we will see and the goal is to get a configuration with the shortest distance between the energy function and the distribution of our data. Similarly as the MSE that we presented in the last section, having a low value of E means that our model has been able to fit well complex data in high-dimensional spaces, the interest of using such energy functions is to be able to use the tools of statistical physics : The interest of this approach is related to the (very) high-dimension spaces that we are reaching giving the data we would like to manipulate. Deep Learning and Neural Networks algorithms are still lacking of a robust theory explaining the behaviour of the models because of the high-dimension of these networks. 
 We will see next, that RBM can be seen as a specific kind of spin glass which brought us back to a well-known statistical physicis model : Ising model.
 
 \begin{figure}
  \centering
  \includegraphics[scale=0.4]{Energy.png}
  \caption{The Energy function is updated to learn complex data in high-dimensional spaces. As for MSE, the distance between the two curves is an indicator of the performance of the model.}
  \label{fig:rbm}
\end{figure}



\newpage

\section{Theory}
\subsection{From Ising model to Hopfield Network}

Ising model is a mathematical model of ferromagnetism in statistical physics. By simple assumptions of interactions between neighbour fixed spins, the model allows identification of phase transition in second dimension.
The spins are arranged in a lattice and discrete variables that represent magnetic dipole moments of atomic spins. The Hamiltoninan of the system can be defined as follow : 

\begin{equation}
H(\textbf{s}) = - J\sum_{i,j} s_i s_j - h\sum_i  s_i   
\label{eq:ef}
\end{equation}

With \(s_{ij}\) the spins, \(J\) the interaction spin-spin and \(h\) the magnetic field.
\bigskip

The theoretical frame of energy based-model of Neural Networks (NN) is coming from Ising Model, often referred as Inverse Ising problems : we are interested to learn the \textit{couplings} between spins in order to generate a specific configuration at equilibrium \cite{tramel}.

Thanks to the work of Hopfield \cite{hopfield}, it has been possible to shape a model mimicking the collective properties of neurons. In this model, the neurons produce memory capable of content-addressable. They are interconnected, creating a network that follow this assertion  : "The ability of large collections of neurons to perform computational task may in part be a spontaneous collective consequence of having a large number of interacting simple neurons."
This last quote make possible the analogy with Ising, we are no longer evaluating spins but neurons and after a redefinition of the parameters, we have at disposal all the tools developed by statistical physics and specifically spin glasses theory.

\begin{figure}
  \centering
  \includegraphics[scale=0.5]{Hopfield.png}
  \caption{A Hopfield Network \cite{figure1} : A fully connected network where each spin represent a neuron associated with two possible states (-1,1) like the Ising Model}
  \label{fig:rbm}
\end{figure}

We consider that each Neurons has two states, communicating or not. The interaction between neurons can be illustrated by a strength of connection T where the value 0 means that the neurons are not connected and 1 they are fully connected. This is our learning rule respecting the Hebbian statement (Neuron that fire together, wire together):
\begin{equation}
\begin{array}{l}{V_{i} \rightarrow 1} \\ {V_{i} \rightarrow 0}\end{array} \text { if } \sum_{j \neq i} T_{i j} V_{j} \begin{array}{l}{>U_{i}} \\ {<U_{i}}
\end{array}
\end{equation}

The energy function of a Hopfield network can be defined as : 

\begin{equation}
E = -\frac{1}{2}\sum_i\sum_j w_{ij} V_i V_j  
\end{equation}

\(W_{ij}\) is the weight matrix describing all the connections of the system.\(V_{ij}\) are vectors that includes all the states of the spins/neurons (-1 or 1).As we can see the formulation is similar to the hamiltonian of the Ising Model described above and with the help of the partition function, it has brought the possibility to identify phase transitions according to tempature. This model has contribute to determinate the average magnetization of a system in a theoretical perspective but experimental results in condensed matter have validated the interest of such a model. In the machine learning perspective, those tools bring the possibility to identify learning phase transitions and the monitoring of the parameters (temperature, size of the network) highlight the existence of an optimum learning phase called compositional phase in the context of this work \cite{emergence}. Furthermore, it is an active domain of research that seems to provide theoretical insights for NN.


 We will focus here on RBM that is  a close model to Hopfield network. Nevertheless, we might have now in mind a little bit of intuition regarding the process involved here and despite some differences, RBM follows similar principles and that we might summarize as :

\begin{itemize}

\item The neurons are equivalent to spins and the synapses can be associated to the connection/interaction between the neurons.We, therefore, redefine the terms of our system.

\item We can define an energy function that is typical in spin glass theory.

\item We can evaluate this energy function through statistical physics theory by using : Boltzmann distribution and the partition function.

\item Learning phase transitions can be identify and parameters can be set to evolve in an optimum learning phase.

\end{itemize}





\begin{figure}
  \centering
  \begin{subfigure}{.35\linewidth}
    \includegraphics[width=\linewidth]{myRBM.png}
    \caption{A Restrictive Boltzmann machine is a biparti graph where the input data is set in the visible layer and the features corresponds to the units of the hidden layer.The matrix \textbf{W} couples the visible and hidden units.}
    \label{fig:data}
  \end{subfigure}
  \begin{subfigure}{.35\linewidth}
    \includegraphics[width=\linewidth]{Logli.png}
    \caption{Gradient ascent consist of reaching the global maximum of the data distribution, this is the way the algorithm learn. }
    \label{fig:rotdata}
  \end{subfigure}
\end{figure}

\subsection{Restricted Boltzmann Machine}

A RBM is an energy based model which can be used as  building block of deep network in the context of unsupervised learning. The model is constituted by two layers of spins (playing the role of neurons). One layer is made by visible units \(v_i\) where the input data pass through, the second layer is constituted by hidden units corresponding to the latent variables that will make possible the generation of data by the RBM. The \textit{couplings} and \textit{local fields} ,which corresponds to the spins of our system, construct an energy function that will be evaluated. The two layers are interconnected but the spins in each layer are independent to each other, this is the specificity of a RBM regarding Hopfield Network and Boltzman Machine (cf: FIG.\ref{fig:rbm}). Therefore,the system can be defined as follows :

\begin{equation}
E(\textbf{h},\textbf{v}) = - \sum_i a_i v_i - \sum_j b_j h_j - \sum_{i,j} v_i w_{ij} h_j
\label{eq:ef}
\end{equation}

 \(a_i\) and \(b_i\) are \textit{external fields} acting respectively on the visible and hidden units. The nodes can have different kind of values depending on the nature of the data set, for simplicity in this case, we will consider binary units as \(h_i,v_i = 0,1\). The probability of a certain configuration is  given by the Gibbs-Boltzmann  density function (taking \(\beta = 1\)) :

\begin{equation}
P(\textbf{h},\textbf{v}) = \frac{e^{-E(\textbf{h},\textbf{v})}}{Z}
\end{equation}

where \( \textstyle Z = \sum_{\textbf{h},\textbf{v}} e^{-E(\textbf{h},\textbf{v})}\) is the \textit{partition function}. The probabilities of activation for visible and hidden spins can be computed as follows (given the independence of units in the same layer):

\begin{align}
P(v_i = 1 | \textbf{h}) &  = \frac{1}{1+e^{-a_i - \sum_{j} w_{ij} h_j}} \nonumber \\
& = sigm \left(a_i + \sum_{j} w_{ij} h_j \right)
\label{eq:act_vis}
\end{align}

\begin{align}
P(h_j = 1 | \textbf{v}) & = \frac{1}{1+e^{-b_j - \sum_i w_{ij} v_i}} \nonumber \\
& = sigm \left(b_j + \sum_i w_{ij} v_i \right)
\label{eq:act_hid}
\end{align}

The neuron activation take place by choosing binary units \(h_j,v_i = 0,1\) in (4) or (5). The external fields \(a_i\) and \(b_i\) adjust the mean of the units while \(w_{ij}\), the weight maxtrix couples the visible and hidden layers (with \textit{sigm} representing the sigmoid function). Several type of activation functions can be used , in the context of our project dRelu function should be investigated.  

The probability distribution of the visible units is given by the following Boltzmann distribution :

\begin{align}
P(\textbf{v}) &  = \sum_{\textbf{h}} P(\textbf{h},\textbf{v}) \nonumber \\
& = \frac{e^{-E(\textbf{v})}}{Z}, \quad Z = \sum_{\textbf{v}} e^{-E(\textbf{v})}
\label{eq:p_model}
\end{align}

In order to optimize the RBM for a given data-set , we need to maximize the likelihood of the training data \(P(\textbf{v}\). In other words, we want to estimate the parameters of a distribution of our data-set in order to fit with our statistical model. 
To perform this, we use the gradient ascent over the log-likelihood (We use "log-l.." to compute sums rather than products), \(\log P(\textbf{v})\) :

\begin{equation}
\frac{\partial \log P(\textbf{v})}{\partial w_{ij}} = \langle v_i P(h_j = 1 | \mathbf{v}) \rangle_{data} - \langle v_i h_j \rangle_{model}
\label{eq:opt}
\end{equation}

where \(\langle \cdot \rangle_{data}\) denotes an average over the distribution of our data-set (\( \textstyle P_{data}(\mathbf{v}) = \frac{1}{N} \sum_{\mathbf{v}_n \in data} \delta (\mathbf{v} - \mathbf{v}_n ) \)) and 
\(\langle \cdot \rangle_{model}\) represent the average over the distribution \eqref{eq:p_model}. Introducing the \textit{learning rate} \(\alpha \) (as a parameter for gradient ascent) we obtain our learning rule for the weights matrix :

\begin{equation}
\Delta \mathbf{W} = \alpha \left( \langle \mathbf{v h}^T \rangle_{data} - \langle \mathbf{v h}^T \rangle_{model} \right)
\label{eq:w_up}
\end{equation}

Additionally, we can get the update rules for the external fields

\begin{equation}
\label{eq:a_up}
\Delta \mathbf{a} = \alpha \left( \mathbf{v}_{data} - \mathbf{v}_{model} \right)
\end{equation}
\begin{equation}
\label{eq:b_up}
\Delta \mathbf{b} = \alpha \left( \mathbf{h}_{data} - \mathbf{h}_{model} \right)
\end{equation}


 As we said, the training consists of performing a gradient ascent. We want to rich an equilibrium between the mean of our data distribution and the mean of the parameters of the model. Nevertheless, the average over the model \(\textstyle \langle \cdot \rangle_{model}\) implies to compute the partition function \( \textstyle Z\) introduced in (4) which is impossible due to the high-dimension involved and the log-likelihood can't be computed directly, we need to find approximations. Monte Carlo based algorithms are the usual solutions to estimate the likelihood. Some other interesting methods exists based on mean field theory and statistical physics \cite{emergence}. However, in this work, we choose to use the \textit{Gibbs Sampling} algorithm.
 
 In order to use RBMs for our project, we need to define a function that will link the visible and hidden layer with the spirit of what was mentioned in the machine learning introduction (we have an input X, we need to define a function to get an output Y with the appropriate characteristics). As we saw the input should be a sequence of strings encoding metabolites and we are still trying to formulate this function. 
 
 In the method developed for the protein generation \cite{Tubiana2018}, this function come as :
 
 \( I_{\mu}(\mathbf{v})=\sum_{i} w_{i \mu}\left(v_{i}\right) \)
 
 This function define what the hidden units receive. \textbf{v} represent the sequence on the visible layers (SMILES in our case) and the computation of the function \textbf{I} is "analogous to the score of a sequence with a position-specific weight matrix".
 Such a score is interesting but the analogy in our case fall short because of the limitations of the SMILES strings. If we are lacking confidence on the capacity of this method to represent molecules in an invariant way, it is difficult to imagine building a function that will track the occurancy of molecules that can be define by different sequences of strings. 
 This problem has been our main brake to go further in the advancement of our problem.
 
 

 
 \newpage
 
 \section{Conclusion}

Our problematic is far to be resolved but many things have been learned and the outcomes of this work kept vivid the enthusiasms of the author. 
We were able to specify our problem by taking into account the different granularity. It appears, under these conditions, necessary to find a strategy that would allow us to move from one space to another without ambiguity (spectrum, structure, taxonomy, bio-activity). We have seen that the SMILES encoding technique seems to be a relevant approach to encode the molecular representation of metabolites, in addition to being a widely used approach in the field, it allows us to make a link with the work that has been done on protein sequences and their representations \cite{Tubiana2018}. As SMILES is a suite of strings, we can imagine using the NLP tools to prepare our databases for use on the visible layer of our RBMs.  
Nevertheless, we still have to formulate the equations that will allow us to go from X to Y as we have seen: this implies going beyond the limitations we have mentioned in relation to SMILES.
On the other hand, in this report, we have not discussed the contributions of the mean field theory and in particular the so-called replica trick\cite{mezard}. This method seems however essential to exploit the compositional phase presented here \cite{emergence}. The author is determined to continue his work in this field, especially since he feels that he is suddenly stopped at the door of one of the deepest questions tackled by statistical physics. It would be interesting to estimate the Z partition function coming from a space as vast as the known molecular space. Moreover, it would also be an opportunity to compare the addition of a spin on our whole system and the influence that it can have on the set of configurations as predicted by mean field approximation\cite{mackay}.

Sometimes in the history of science, we find that ideas travel and become clearer through time. This phenomenon is well known to physicists and perhaps the atomic intuition that we found asleep and already in Lucretia's De Rerum de Natura is a good illustration of this.
To be interested in plants, as we have seen, is also to make such a journey and perhaps it is possible to find a way to reconcile thousand-year-old intuitions with the tools available today. This journey into molecular space is all the more exciting and, to all intents and purposes, it perhaps allows us to remember that observation is the basis of all science. 

\section{Acknowledgments}
This work was done under very particular conditions and great difficulties were encountered. Nevertheless, I would like to warmly thank Pierre-Marie Allard who proved to be an indispensable companion allowing me to be initiated to his field. His support, his open-mindedness and his kindness were really precious for this work. 

\newpage

\printbibliography

\end{document}


