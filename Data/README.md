(TW: Sex, Rape)

## OITNB Sexual Encounters Dataset

This dataset focuses on the onscreen physical sexual/affectionate encounters (i.e. kissing, touching, sexual acts, etc) shown during Netflix’s Orange is the New Black (OITNB) series.

**Criteria to be included:**
* Act must involve at least one named character. 
* Act must be the focus of the scene, not in the background.
* Characters must engage in an affectionate/sexual act. This is defined as kiss/kissing, groping/touching, oral sex, hand/finger stimulation, and/or penetrative sex. Hugging and other affectionate acts are not included as there are many and the focus for the data is queer on-screen sexual representation.
* Act must be shown on screen, not an “implied sex” or “post-sex” scene where people are in bed together, nude, etc. Phone/verbal sex are also not included, even though those scenes (Blanca/Diablo, Lorna/Vince) were very graphic.
* Act must include more than one un-related person. Masturbation was regrettably not included, it probably would have been interesting. Affectionate acts between parents and their children are also not included, with the exception of informal parental figures such as Vee/RJ and Red/Nicky
* Significant dialogue during an act is cut out. Some dialogue is acceptable if the act is still the focus. This is subjective, but we did our best to limit any simultaneous dialogue to that related to the encounter instead of dialogue used to further develop the plot. 

All acts meeting the above criteria were manually recorded to create the data. This includes affectionate encounters between friends, inappropriate patdowns, transactional sex, rape, etc. The nature of a relationship was not a factor in the inclusion of the encounter in the dataset, although sometimes captured in other variables. 

**Data Dictionary:**

| Variable       | Description           | Data Type  |
| :------------- |:-------------| :-----|
| Season     | Season number (1-7). | Integer |
| Episode    | Episode number (1-13). | Integer |
| Title    | Title of episode. | String |
| Person1    | First person in encounter, alphabetically.  | String |
| Person2    | Second person in encounter, alphabetically.  | String |
| Start    | Starting timestamp of encounter, from the end (it was easier to look at the “time remaining” while recording).   | Timestamp (MM:SS) |
| End    | Ending timestamp of encounter, from the end (it was easier to look at the “time remaining” while recording).   | Timestamp (MM:SS) |
| Duration    | Duration of encounter (seconds). Acts (typically kisses) shorter than 1 second were recorded with an `End` time rounded to have a minimum duration of 1 second.   | Timestamp (MM:SS) |
| Location   | Where the encounter took place, one of the following: <ul><li>Flashback – For events that took place in a flashback scene</li><li>Litchfield – For events that took place within the prison (including Max and the ICE facility)</li><li>Outside – For events taking place outside the prison</li></ul>   | String |
| Type | Description of act(s) in encounter. Five categories emerged:<ul><li>Groping/Touching – Grabbing or touching of the chest, thighs, butt, or hips that is sexual in nature and not solely a “grip” for another sexual act. Also includes things like undressing or butt slaps.</li><li>Kiss/Kissing – Includes kisses of all intensities on any location (lips, cheek, forehead, hand, etc). </li><li>Hand/Finger stimulation (genital receiving) – touching of the receiving genital with fingers or hand. This includes clitoral stimulation/”fingering” and “handjob” acts. Interestingly, there was no mutual stimulation shown on-screen so the (genital receiving) specification format worked. Note that the series has mostly cis narratives, genitals are assumed if not explicitly shown.</li><li>Oral sex (genital receiving) – Oral sex performed on the receiving genital. Note that the series has mostly cis narratives, genitals are assumed if not explicitly shown.</li><li>Penetrative sex (what penetrates) – Penetrative sex with the specified body part/object used in the act. Interestingly, no anal sex was shown on-screen, all penetrative sex was vaginal.</li><li>Other – A small number of encounters did not fit the five categories and were classified as “other” with a description in the `Notes` variable.</li></ul>| String|
| Queer     | Indicator variable for whether an encounter is lesbian/gay/queer (1) or not (0).<br><br>Queer designation is determined based on the encounter shown and the explored/assumed gender identities in the character’s narratives to date. For example, if at the time the encounter is shown both characters have had narratives that suggest they identify as cis women, the encounter would be labeled as queer regardless of their explored sexual orientations. The focus of the dataset is queer on-screen sexual representation, so while technically a “straight” encounter including a bisexual character is “queer”, this variable is based solely off the encounter shown and known gender identities. Similarly, affectionate acts between friends can be labeled as “queer” even if the characters motivations are strictly platonic. | Binary |
| Transactional     | Indicator variable for explicit/obvious references that an encounter is transactional in nature (1), or not (0).  <br><br>OITNB is a drama that depicts and explores many topical and complex issues. Trading a sexual act for drugs is easy to classify as transactional, but other relationships have complexities that make it harder to tease out motivations. For example, Aleida is shown to be in situations with both Cesar and Hopper where she uses sex/sexuality to ensure support for her and her children. Sometimes the dialogue and/or body language prior to an act makes this apparent and it is labeled as such, but other times it is unclear. These ambiguous encounters are not labeled as transactional, even though given the relationship history they potentially could be. Similarly, Linda likely used sex to gain protection from Boo in the riot, but since this was not explicit it was not labeled as such. Basically, it’s hard to parse out motivations from character dynamics that are intentionally complex, and this is a subjective label specific to my research questions. Feel free to disagree with or disregard labels. | Binary |
| NonConsentual     | Indicator variable for explicit/obvious references that an act is non-consentual and/or rape. <br><br>OITNB is a drama that depicts and explores many topical and complex issues, with rape being one of them. Some narratives portray this explicitly while others are intentionally ambiguous. The prison setting also complicates the designation. While technically all CO/inmate sexual encounters are rape, the series frames some as being motivated by love (e.g. Daya/Bennett) or manipulated (Daya/Pornstache) and were not labeled as non-consentual. Pennsatucky and Donuts relationship is also intentionally complex, each of their encounters are labeled based on the perception/framing in the moment. Like `Transactional`, this is a subjective label specific to my research questions. I understand the seriousness of minimizing rape and that is not the intent. | Binary |
| Notes    | Any additional information about the encounter, or clarifying details.  | String |

Data recorded April 2020 (initially 2019 but updated for refined criteria and Netflix increasing episode length (suspect additional credits were added at end of all episodes).

This data focuses on encounters that are sexual-in-nature given the opportunity the series provides through its groundbreaking portrayal of queer relationships. We recognize that this is sex-normative and that there are other just as intense forms of intimacy one could choose to engage in. Much love to the ace/aro community, whose [portrayal in media](https://azejournal.com/article/2018/6/29/creating-ace-space-in-the-media) also desperately needs to be explored.

## OITNB Episode Length Dataset

This is a supplemental dataset with the total episode length for all OITNB episodes (not just ones with an on-screen sexual/affectionate encounter). This set can be merged into the Sexual Encounters dataset for use in analyses where normalization is needed. 

**Data Dictionary:**

| Variable       | Description           | Data Type  |
| :------------- |:-------------| :-----|
| Season     | Season number (1-7). | Integer |
| Episode    | Episode number (1-13). | Integer |
| Title    | Title of episode. | String |
| EpLength    | Total length of episode. | Timestamp (H:MM:SS) |
