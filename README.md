# nagasaki-TMGH-harvard-csl
Nagasaki University Harvard – Cite Them Right 12th, 3+ authors et al.
A Harvard-style CSL (Citation Style Language) style customized to match the master's dissertation guidelines of Nagasaki University's School of Tropical Medicine and Global Health (TMGH).

File: nagasaki-university-harvard-cite-them-right-12th-et-al-3.csl
Base style: Cite Them Right 12th edition (author-date/Harvard) (official Zotero Style Repository version)
id: http://www.zotero.org/styles/nagasaki-university-harvard-cite-them-right-12th-et-al-3
Why this customization is needed (peculiarities of the Nagasaki University guideline)
Section 9. REFERENCES of the TMGH Guidelines for Preparation of Master's Dissertation for Students (2026 edition) specifies an in-text citation rule that differs from the standard Cite Them Right style:

In the text, the surname of the author is given in brackets with the year of publication, e.g., (Smith, 1979), except when the author's name is part of the sentence, e.g., 'Smith (1979) stated that….'. Where there are two authors, both surnames are given and the ampersand (&) is used in place of 'and' – e.g. (Smith & Brown, 1979). Where there are more than two authors, the first name only followed by et al is cited: (Smith et al, 1979).

This passage reveals three points where Nagasaki University's convention diverges from standard Cite Them Right (which uses "and" and switches to et al. only at 4+ authors):

Switch to et al. from 3 authors onward (standard Cite Them Right uses 4+)
Use "&" instead of "and" for two authors
This rule applies only to in-text citations — the reference list format is not addressed, so the reference list is assumed to follow standard Cite Them Right unchanged
Note that the guideline's own worked example, (Smith et al, 1979), omits the period after "et al". This is treated as an inconsistency in the university guideline text; per the user's explicit decision, this style keeps the standard Cite Them Right form "et al." (with period).

Changes from the base style
The <citation> element and the <bibliography> element use fully independent name-rendering macros (author-short for citations, author for the bibliography), so only the in-text citation (citation) side was changed — the reference list (bibliography) side is completely unchanged.

Item	Original Cite Them Right 12th	This custom style	Where it's implemented
Author count that triggers et al.	4+	3+	<citation et-al-min="3" et-al-use-first="1" ...>
Two-author connector	and	&	<name form="short" and="symbol" .../> in the author-short macro
Missing-date rendering	no date	n.d.	<text term="no date" form="short"/> in the year-date macro (uses the abbreviated form already defined in the official CSL en-GB locale)
Reference list: author truncation, name order, initials, year position, title case, italics, volume/issue/page, DOI/URL/accessed date, per-type formatting, punctuation, sort order	—	Unchanged (<bibliography and="text" et-al-min="4" et-al-use-first="1"> left exactly as in the original)	—
In-text citation output examples
Number of authors	Parenthetical	Narrative
1	(Smith, 2020)	Smith (2020)
2	(Smith & Jones, 2020)	Smith & Jones (2020)
3+	(Smith et al., 2020)	Smith et al. (2020)
Missing date	(Smith, n.d.)	Smith (n.d.)
Multiple works, same author & year	(Smith, 2020a) / (Smith, 2020b)	Original disambiguation logic preserved unchanged
A technical limitation of CSL: under CSL 1.0.2, parenthetical and narrative citations are rendered through the same macro (author-short), so "&" and "and" cannot be automatically switched based on context. The official APA CSL (apa.csl) has the same constraint and uses and="symbol" uniformly everywhere; this style follows the same convention and uses "&" in both forms.

Installing in Mendeley / Zotero
Mendeley Reference Manager: go to "Citation styles" → "Install more styles / Get more styles", then either point it at the local .csl file or paste a GitHub Gist raw URL into the search box to install.
Zotero: Preferences → Cite → Styles → "+", then select the .csl file.
Source documents
Admin_doc/Procedure-and-Criteria-for-Plagiarism-for-Students_2026 .pdf (plagiarism screening procedure; mandates use of the Harvard referencing system)
Guidelines-for-Preparation-of-Masters-Dissertation-for-Students_2026 (1).pdf (Section 9. REFERENCES specifies the exact in-text citation rules)
