# Is Crime Up?

An interactive comparison of what Americans say about crime and what crime victimization surveys found. Students make three guesses, then see 35 years of Gallup polls next to the violent victimization rate. By Gwen Sharp, as a companion to Chapter 13 (Deviance) of *A Sociology Experiment*.

**Live site:** https://gsharpokie.github.io/crime/

## What it does

- **Three guesses first:** whether violent crime is higher or lower than in 1993, what share of Americans said crime was rising in 2023, and whether people see more crime in the country or in their own area.
- **Two charts on one timeline:** the share saying there’s more crime than a year ago (in the U.S. and in their own area), and the violent victimization rate. Students can pick any year to see all three numbers. A table of the numbers is included for screen reader users.
- **The fuller picture:** crime didn’t fall every year (it rose in 2020–2022), the 2025 figures are the lowest in decades, and perceptions improved in 2025.
- **Discussion questions,** including the availability heuristic from psychology.

## For instructors

The charts stay hidden until the third guess so they don’t give away the answers. To open the page with the charts showing (for example, on a projector), add `#charts` to the link: https://gsharpokie.github.io/crime/#charts

## Data

- **Gallup** annual Crime survey: “Is there more crime in the U.S. than there was a year ago, or less?” (1989–2025) and the same question about “your area” (2000–2025). Gallup didn’t ask every year. Source: https://news.gallup.com/poll/697124/crime-seen-less-serious-second-straight-year.aspx
- **Bureau of Justice Statistics,** *Criminal Victimization, 2024* (NCJ 310547), appendix table 1: violent victimizations per 1,000 people age 12 or older, 1993–2024. 2006 is left out because BJS says it isn’t comparable. https://bjs.ojp.gov/document/cv24.pdf
- 2025 context: BJS preliminary NCVS estimates (October 2026) and FBI figures as reported by the Associated Press (August 14, 2026).

## Updating it each year

Gallup publishes its Crime survey each fall, and BJS publishes *Criminal Victimization* each fall. Near the top of the `<script>` section of `index.html`:

- `const NAT = {` and `const LOC = {` hold the Gallup percentages by year. Add the new year at the end, like `,2026:52`.
- `const NCVS = {` holds the victimization rate by year. **Don’t add 2025 or later to this line without checking:** BJS redesigned the survey in 2024, and it says estimates from the new version aren’t comparable to the old ones. If BJS publishes a bridged series, use that.
- If you add a year past 2025, change `Y1 = 2025` and the `max="2025"` on the year slider.
- The summary sentences (“26 of the 29 surveys,” the 71% drop, the average gap) are calculated from the data, so they update on their own. The “fuller picture” paragraphs are plain text and need editing by hand.

To edit, open `index.html` on GitHub, select the pencil icon, make the change, and select **Commit changes**.

## Turning on the site (one time)

Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, and select **Save**.

The page’s “Suggest a correction” link opens a new issue in this repository, so keep Issues turned on.

## Author

Created by Gwen Sharp ([@gsharpokie](https://x.com/gsharpokie)).

## License

© 2026 Gwen Sharp. Licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/): you may share and adapt it for noncommercial purposes with credit. See [LICENSE](LICENSE). The survey figures belong to their sources; this license covers the page’s design, text, and code.
