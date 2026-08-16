# AppADay 101 &mdash; Liturgical Season Companion

**Live:** https://augustineiacopelli.github.io/appaday-101-liturgical-season-companion/

**Portfolio:** https://augustineiacopelli.github.io/appaday/

Open it and see today's place in the Church year. The season and the vestment color worn, the week within that season, the Sunday cycle A/B/C and the weekday cycle I/II, and the next solemnity or feast with a countdown. Every date is computed on the device from the Computus, so the whole calendar works offline and resolves any day of any year.

## What it does

The liturgical year is drawn as a ring, because it is genuinely a cycle rather than a list. Each season is an arc scaled to its true length, and a marker sits on the day you are looking at. Tap any arc to jump to the first day of that season.

The page takes its color from the day. Green through Ordinary Time, violet through Advent and Lent, rose on Gaudete and Laetare, red on Palm Sunday and Good Friday and Pentecost and the martyrs, white through Christmas and Easter. What you see is what is worn.

Five panels sit underneath. **Seasons** lays out every season of the current liturgical year with its dates, length, and color. **Feasts** lists every celebration in the year down through the optional memorials, marks which are actually kept and which are outranked by the day they fall on, notes the holy days of obligation, and flags the years when a precept is lifted. **Cycles** shows ten liturgical years around this one with their Sunday and weekday lectionary cycles and Easter dates. **Computus** shows the arithmetic your device just ran, every intermediate value, and Easter across twenty years. **Calendar** carries the three settings that move.

Arrow keys step a day at a time. Pressing T returns to today.

## The calendar underneath

Easter is found with the Meeus, Jones and Butcher algorithm for the Gregorian calendar, and every movable date in the year hangs off it. The First Sunday of Advent is the fourth Sunday before Christmas. Ordinary Time is numbered in two stretches: the first counted forward from the week containing the Baptism of the Lord, the second counted backward from Christ the King so it always closes on week 34.

Precedence follows the Table of Liturgical Days so that the right thing wins on a crowded day. A solemnity displaces a Sunday in Ordinary Time; a Sunday of Advent, Lent, or Easter displaces a feast; the Triduum displaces everything. When a celebration is set aside, the app says so and shows the color worn in its place.

Below the feasts sit the memorials, and they behave differently from each other. An obligatory memorial takes the day on an ordinary weekday, but yields to the privileged weekdays of Lent, of 17 to 24 December, and of the Christmas octave, where it drops to a commemoration. An optional memorial never takes the title at all, because the choice belongs to the priest; it is offered instead as something that may be kept. Neither survives a Sunday, a solemnity, or a feast.

Two things that get confused are kept separate here. When the Assumption, All Saints, or Mary, Mother of God falls on a Saturday or a Monday, the United States lifts the **obligation** but still keeps the **solemnity** in white. That is not the same as a feast being omitted because the day outranks it.

## Settings

Three celebrations move depending on where you are, and all three default to United States practice.

The Epiphany can be kept on 6 January or transferred to the Sunday between 2 and 8 January. This also sets the Baptism of the Lord, which closes Christmas Time, and it matters: in years when the transferred Epiphany falls on 7 or 8 January, the Baptism moves to the following Monday rather than the following Sunday.

The Ascension can be kept on the Thursday forty days after Easter or transferred to the Seventh Sunday of Easter. Corpus Christi can be kept on the Thursday after Trinity Sunday or on the following Sunday.

Choices are stored in `localStorage` on the device.

## Scope

This follows the General Roman Calendar with the United States proper calendar layered on top, covering seasons, ranks, colors, cycles, solemnities, feasts, and both obligatory and optional memorials. In a given liturgical year that is roughly 245 celebrations.

It is not an ordo. It does not carry local patrons, diocesan propers, votive Masses, or the transfers a particular year may require, and where several optional memorials share a date it lists them all rather than choosing. The celebration data was entered by hand and is worth checking against a current ordo before anyone relies on it; a parish or diocesan ordo governs.

## Build

One self-contained `index.html`. Vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies beyond Google Fonts. Nothing is fetched at runtime, so once the page is open every date in every year resolves offline.

Verified with 247 behavioral assertions across twenty suites, including the Computus checked against published Easter dates from 1900 to 2100, season boundaries and week numbering, precedence, the Baptism edge case in 2024, colors including rose and red, cycle rollover at Advent, the memorial ranks and their suppression rules, and sweeps of 720 dates across twelve years and 2,016 dates across six with no crashes and no Ordinary Time week outside 1 to 34.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), a daily discipline project by Augustine Iacopelli.
