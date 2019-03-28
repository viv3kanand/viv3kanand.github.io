---
layout: post
title:  "Recombinant prion protein QC"
date:   2017-06-07 12:01:00
author: ericminikel
location: Cambridge, MA
thumb120: http://www.cureffi.org/media/2017/06/prp-qc-thumbnail.png
summary200: "We've done a battery of quality control checks on the recombinant prion protein that we produce in-house at Broad."
---

Sonia and I are continuing to seek out new ways to discover small molecules that bind PrP. Every time we meet with a new potential collaborator, or someone who we're asking to teach us a technique, or a particularly astute candidate for the [open position in our lab](https://goo.gl/DvzPO4), their first question is always (justifiably) what have we done to make sure our protein is good? I finally decided to just compile the answer to that question into this blog post and send people here.

### How we make recombinant PrP

We purify recombinant PrP using essentially the [Rocky Mountain Recombinant protocol](/2014/07/30/recombinant-prion-protein-rocky-mountain-style/), with a few minor modifications (discussed further below). We use "full-length" (HuPrP23-230, lacking the signal peptide and GPI signal found in the mammalian gene and thus corresponding to the mature, post-translationally cleaved protein) or N-terminally truncated (HuPrP90-231) protein. These constructs are *not* tagged nor cleaved, and thus retain an N-terminal methionine not present in mature PrP expressed in mammalian cells. The purification relies on PrP's intrinsic affinity for metals, allowing it to be purified like a His-tagged protein even though it lacks a His tag. The proteins are expressed in *E. coli*, and the proteins in inclusion bodies are isolated by fractioning, denatured in guanidine, loaded onto Ni-NTA beads, refolded on an AKTA fast protein liquid chromatography (FPLC) machine, and eluted with imidazole.

The minor changes we've made versus the [original protocol](/2014/07/30/recombinant-prion-protein-rocky-mountain-style/) are:

1. **Increased protein loading.** We have on some occasions increased the amount of protein we try to load onto the beads. The original protocol says not to put more than the equivalent of 750 mL of bacterial culture into a 26x20 column containing 54g (which is tens of mL) of Ni-NTA resin, with a typical yield being maybe 50 mg. That means you're trying to bind on the order of 1 mg of protein per mL of resin. For comparison, For instance, [Qiagen's specs for the Ni-NTA superflow resin](https://www.qiagen.com/us/shop/sample-technologies/protein/expression-purification-detection/ni-nta-superflow/#technicalspecification) advertise a binding capacity of up to *50* mg protein per mL of resin. I was inspired to get slightly more adventurous and in PrP batch 19 I tried loading 2 L of bacterial culture worth of solubilized inclusion bodies onto one column, and indeed, I got a yield of 190 mg.
2. **Higher pH elution.** The [original protocol](/2014/07/30/recombinant-prion-protein-rocky-mountain-style/) calls for elution in a gradient to 500 mM imidazole at pH 5.8. This practice appears to date back to [[Zahn 1997]]. The [QIAExpressionist](https://www.qiagen.com/us/resources/resourcedetail?id=79ca2f7d-42fe-4d62-8676-4cfa948c9435&lang=en) notes that you can elute His-tagged proteins with *either* acid (to protonate the histidines that bind the nickel) *or* imidazole (to compete away the histidines), but the idea of using acidic pH and imidazole *at the same time* is bizarre. Free imidazole actually has a higher pKa than histidine (about 7 vs. 6), so by the time you've protonated the protein's histidines enough to reduce their binding, the imidazole should be so thoroughly protonated that it no longer competes. At pH 5.8, one can calculate that ~95% of the imidazole should be protonated. Indeed, even the process of making a 500 mM imidazole solution at pH 5.8 just feels wrong: you're standing there at the pH meter forever, dumping in milliliters upon milliliters of 37% HCl, protonating all that imidazole that's supposed to elute your protein. We therefore did the experiment of trying to elute PrP at pH 5.8 without imidazole and, as expected, nothing eluted &mdash; the QIAExpressionist says you need a pH more like 4.5 if you want to elute with pH alone, and once we lowered the pH to 4.5, we finally saw our protein elute. With a different batch, we then tried eluting in 500 mM imidazole at pH 8.0, and we saw robust elution. I concluded that the low pH in the original protocol is not contributing to elution efficiency. Indeed, I suspect the only reason it even works at all is that it's run as a gradient, so that as the elution buffer gets gradually titrated into the refolding buffer, the pH stays high enough long enough that you have a window where the effective un-protonated imidazole concentration is just high enough to elute the protein. Thereafter, we started eluting all our protein in 500 mM imidazole at pH 8.0, although we've since noticed that we may be getting ~10% reduced cysteines (see below) at this pH, so in the future we may shift down a bit to pH 7.0 or something.

Since [our first batch at Broad](/2015/12/22/our-first-recombinant-prp-prep-at-broad/) a year and half ago, we've run the protocol about 20 times, making various constructs (HuPrP23-230, HuPrP90-231, SHaPrP90-230, and MoPrP23-230, as well as HA- and SNAP-tagged PrPs which have been less successful) dialyzed into different buffers (phosphate, HEPES, different pHs, with or without EDTA). We have gotten excellent yields, of about 50 - 100 mg per liter of bacterial culture. We have never performed an exhaustive set of QC experiments all on a single batch of protein, but we've done a patchwork of experiments on different batches to convince ourselves that the protein we're making is legit.

### Circular dichroism to interrogate secondary structure

As described in [this blog post](/2015/12/27/circular-dichroism-on-recombinant-prp/), we performed circular dichroism (CD) on our first Broad-purified batch of PrP. CD measures absorption of circularly polarized UV light to gain information about protein secondary structure. Here's the CD spectrum we obtained for HuPrP23-230:

![](/media/2015/12/protein-cd-spectrum.png)

It is consistent with substantial alpha helical content, as alpha helices tend to give local minima around 208 and 222 nm. 

### Melting temperature by a few methods

The literature gives a range of melting points for PrP, from about 66 - 71&deg;C [[Nicoll 2010], [Calzolai & Zahn 2003]]. We've measured the melting point of our PrP by three methods.

First, we used CD (see above). As [covered here](/2015/12/27/circular-dichroism-on-recombinant-prp/) we monitored 208 and 222 nm &mdash; two wavelengths indicative of alpha helical content &mdash; while heating the protein from 20 to 90&deg;C:

![](/media/2015/12/prp-melting-curve.png)

The results show a melting point in the mid to high 60s &deg;C, consistent with expectation.

Next, we used differential scanning calorimetry (DSC), which directly monitors protein unfolding via heat capacity &mdash; the amount of heat energy needed to raise the temperature each degree. As described [here](/2016/04/27/differential-scanning-calorimetry/) HuPrP23-230 gave us a melting point around 67&deg;C, which dropped slightly but not catastrophically after 24+ hours in up to 4% DMSO:

![](/media/2016/04/dsc-results.png)

Finally, and as I'll explain more in an upcoming post, we have also performed a battery of differential scanning fluorimetry (DSF) experiments, which monitor the emission of a dye that fluoresces when bound to hydrophobic patches of unfolded proteins in order to infer melting point. 

Here's a randomly chosen melting curve from a plate of PrP batch 13 (HuPrP90-231) in 20 mM HEPES, 25 mM NaCl, 1 mM EDTA at 50 &mu;M, melted in a white lightcycler plate in a Roche Lightcycler 480 on the protein melt program, with 10X Sypro Orange dye and 2% DMSO:

![](/media/2017/06/ts00027-b6-example-curve.png)

The midpoint of the increase in fluorescence looks to be somewhere in the low 60s &deg;C.

Remember that each of these three methods is measuring something different: heat capacity (DSC), secondary structure (CD), and exposure of hydrophobic residues (DSF), so it's not a big deal if we don't get the *exact* same melting point from the three methods, but it is reassuring that we see results that are all roughly consistent with one another.

### TROSY NMR spectrum and stability

We've produced two batches of <sup>15</sup>N-labeled PrP in order to do 2D protein-observed NMR. One batch was HuPrP23-230 at pH 5.8, described [here](/2016/04/13/charting-the-prp-archipelago-with-trosy/). It was possible to assign some of the peaks, but the plot was a bit crowded, in part because many of the amino acids from the unstructured region of the protein had peaks very close to each other. We later made a batch of <sup>15</sup>N-labeled HuPrP90-231 which I dialyzed into 20 mM HEPES, 25 mM NaCl, and 1 mM EDTA at pH 6.8. It was thus somewhat closer to the construct (HuPrP121-230) and conditions (pH 7.0 in phosphate buffer) used in one reported structure, [1HJM](http://www.rcsb.org/pdb/explore.do?structureId=1HJM) [[Calzolai & Zahn 2003]]. Our NMR spectrum, obtained with 50 &mu;M protein using TROSY on a Bruker 600 MHz spectrometer, proved to line up beautifully with the [reported peaks](http://www.bmrb.wisc.edu/data_library/summary/index.php?bmrbId=5713) from the 1HJM structure. To be able to compare HSQC and TROSY, I added 0.2 to the <sup>1</sup>H HSQC shift and subtracted 1 from the <sup>15</sup>N HSQC shift. Once I did this, the reported peaks and our peaks line up very nicely:

![](/media/2017/06/rprp00014-day0-vs-calzolai.png)

The above is at day 0, with 2% DMSO. To test whether our protein is stable enough in these conditions to 	wait in the queue for a screen to run, I let it sit at room temperature for four days, acquiring a TROSY spectrum again on day 2 and day 4:

![](/media/2017/06/rprp00014-day0-vs-2-vs-4.png)

If you feel you're squinting and can't really make out the different days, you can't &mdash; they overlap perfectly. The spectrum didn't change a bit, which is very reassuring about the stability of this protein in this buffer with 2% DMSO. As a positive control to check that the spectrum would change if the protein were denatured, I then boiled the protein by heating to 95&deg;C for 5 minutes, whereupon it almost instantly formed visible white precipitate. When I returned it to the NMR spectrometer, here's what I saw (at the same zoom level as above):

![](/media/2017/06/rprp00014-day4-post-boil.png)

So yes, the spectrum does go away if the protein is precipitated.

We haven't done the analogous experiment for HuPrP23-230.

### Dynamic light scattering to test for aggregation

Dynamic light scattering (DLS) is a technique for determining the size of particles in solution, based on the principle that larger particles scatter more light. Our labmate Zarko Boskovic taught us to do DLS, starting with our PrP batch #19. This was a batch of HuPrP90-231 where I ambitiously combined 2 liters of bacterial culture worth of inclusion bodies into a single column to see if I could recover the full yield. (We were taught to only use 750 mL equivalent per column, but the loading capacity of Qiagen superflow Ni-NTA beads is advertised as being much higher, so we wanted to try). Indeed, the yield was 190 mg, eluted in a small volume at a concentration of 112 &mu;M (about 1.8 mg/mL). It was dialyzed into 20 mM HEPES, 25 mM NaCl, 1mM EDTA pH 6.8 and freeze/thawed before doing DLS. If there were ever a batch of PrP to aggregate, you might worry it would be this one. But the DLS results supported ~99% of particles being of ~4.3 nm radius, consistent with a PrP monomer:

![](/media/2017/06/DLS_PrP19_2017-03-20-E7-histo.png)

Large aggregates were present, but only accounted for 1.3% of the mass. These could presumably be removed by spinning the protein through a 100 kDa cutoff PALL filter, which we do routinely for RT-QuIC but had not done for DLS.

As you can see, the particle size estimated from the light scattering has quite a range, with 4.3 nm diameter being the mean. The software estimates that this corresponds to a 21 kDa molecular weight; our HuPrP90-231 monomer should be 16 kDa. But my understanding is that this is well within the error of the method; indeed, some folks I spoke with believed that for a protein of this size, DLS could not even distinguish a monomer from a dimer.

### Coomassie gels to assess purity

My colleague Emily Ricq ran a few of our different protein batches on a Coomassie gel to assess their purity, for instance:

![](/media/2017/06/elr56_prp_coomassie.png)

All were the expected molecular weight (~22 kDa for full-length and ~16 kDa for truncated) and no other bands were really visible at all, so the purity is probably at least 95%.

One peculiarity she noted was that PrP19 (the high concentration HuPrP90-231 mentioned above) when run on a gel after boiling in SDS had about 10% apparent dimer content. She hypothesized these were intermolecular disulfide dimers formed during the boiling in SDS for the gel, and sure enough, when she alkylated the protein with iodoacetamide prior to boiling, the dimers went away. So the conclusion, then, is that at least this one batch of protein has about 10% of the protein in a reduced state (PrP's native state is to be oxidized). A possible reason for this is that this batch was refolded at pH 8.0 and eluted in a gradient to 500 mM imidazole at pH 8.0 before being dialyzed into a pH 6.8 buffer. The pH 8.0 buffers are close enough to the cysteine side chain pKa of 8.37 ([source](http://academics.keene.edu/rblatchly/Chem220/hand/npaa/aawpka.htm)) that some of the intramolecular disulfide bonds may not have formed properly. In the future we may try eluting or even refolding at a lower pH to minimize this problem.

### Positive control binders

There aren't any really good, specific, 1:1 small molecule binders of PrP &mdash; that's the whole point of our small molecule effort &mdash; but we have tested a few positive controls to see if we see binding. As explained [here](/2016/09/12/isothermal-titration-calorimetry/), we did observe FeTMPyP binding to PrP as others have observed, with a Kd of ~20 &mu;M. More recently we also tested heparin, which is one of the several sulfated glycans shown to bind PrP [[Caughey 1994]]. The [heparin we bought from Sigma](http://www.sigmaaldrich.com/catalog/product/sial/h3393?lang=en&region=US) was purified from a natural source (porcine intestine) and comes with no claim as to even an average molecular weight, but if we assume as a wild guess a molecular weight of 10 kDa, then we saw a Kd of 51 nM for binding to HuPrP23-230 by isothermal titration calorimetry. This was batch 22, HuPrP23-230 at 10 &mu;M dialyzed into 20 mM sodium phosphate buffer at pH 7.0.

![](/media/2017/06/heparin_prp_itc.png)

### Sensitivity to prions in RT-QuIC

Another good test of one's recombinant PrP quality is the ability to specifically detect prions in [RT-QuIC](/2014/06/19/rt-quic-protocols-in-detail/). We had 12 de-identified human brain samples that a collaborator had sent us for our research, and we were blinded as to which individuals had prion disease and which did not. We used our PrP batch 6 (HuPrP23-230) to run an RT-QuIC with brain homogenates from all 12 samples at a 10<sup>-3</sup> down to a 10<sup>-9</sup> dilution, plus a buffer-only control. We did this in a 384-well plate with a 25 &mu;L reaction volume and a 0.5 &mu;L seed, thus making it possible to fit this whole matrix of experiments onto a single plate. (For RT-QuIC aficionados, this experiment was done at 42&deg;C in a Fluostar Optima platereader shaking at 600 rpm 1 minute on, 1 minute off; the master mix was "low salt" (~130 mM NaCl just from PBS) and the brain homogenates had 0.1% SDS.) Here's a scatterplot of the times at which positive ThT fluorescence was detected:

![](/media/2017/06/rtq00041-t-up-25.png)

As you can see, fluorescence increased by 25% over baseline within a few hours at strong dilutions, and within a day or two at lower dilutions, for 10 of the samples, while the final two samples were negative out to at least 6 days, with only a single well flukily turning positive. We concluded these two samples were the non-prion controls, and the collaborator who provided the samples subsequently confirmed this over email. Thus, our protein (or at least this one batch) seems suitable for detecting prions by RT-QuIC.

### Conclusions

Overall it appears that we've succeeded in producing properly folded recombinant PrP here at the Broad, and we're now using this PrP for a wide variety of different assays. But biology being what it is, there's still no guarantee that any new experimental conditions &mdash; different buffers, different concentration, different pH &mdash; won't affect our protein, and it's still important to do additional QC experiments 


[Caughey 1994]: https://www.ncbi.nlm.nih.gov/pubmed/7511169 "Caughey B, Brown K, Raymond GJ, Katzenstein GE, Thresher W. Binding of the protease-sensitive form of PrP (prion protein) to sulfated glycosaminoglycan and congo red [corrected]. J Virol. 1994 Apr;68(4):2135-41. Erratum in: J Virol 1994 Jun;68(6):4107. PubMed PMID: 7511169; PubMed Central PMCID: PMC236688."

[Calzolai & Zahn 2003]: http://www.ncbi.nlm.nih.gov/pubmed/12826672 "Calzolai L, Zahn R. Influence of pH on NMR structure and stability of the human prion protein globular domain. J Biol Chem. 2003 Sep 12;278(37):35592-6. Epub 2003 Jun 25. PubMed PMID: 12826672."

[Nicoll 2010]: http://www.ncbi.nlm.nih.gov/pubmed/20876144 "Nicoll AJ, Trevitt CR, Tattum MH, Risse E, Quarterman E, Ibarra AA, Wright C,  Jackson GS, Sessions RB, Farrow M, Waltho JP, Clarke AR, Collinge J. Pharmacological chaperone for the structured domain of human prion protein. Proc  Natl Acad Sci U S A. 2010 Oct 12;107(41):17610-5. doi: 10.1073/pnas.1009062107. Epub 2010 Sep 27. PubMed PMID: 20876144; PubMed Central PMCID: PMC2955083."

[Zahn 1997]: http://www.ncbi.nlm.nih.gov/pubmed/9409760 "Zahn R, von Schroetter C, Wüthrich K. Human prion proteins expressed in Escherichia coli and purified by high-affinity column refolding. FEBS Lett. 1997 Nov 17;417(3):400-4. PubMed PMID: 9409760."


