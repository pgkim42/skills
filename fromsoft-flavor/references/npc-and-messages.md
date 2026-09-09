# NPC dialogue and player-message devices

Corpus: ~60 official EN lines from 14 NPCs (DS1, DS3, BB, ER, Sekiro) plus the verified Elden Ring message grammar. Quotes are calibration only; never reproduce them in output.

An NPC line is built from slots: [interjection or vocative] + [terse observation] + [one fact] + [consequence or withheld hint] + [laugh or farewell]. Use two to four slots, not all five.

## Openers and address

- Vocative-first fragment, then a short observation. "Graceless Tarnished. / What is thy business with these thrones?" (ER, Morgott) · "Greetings. / Traveller from beyond the Fog. / I am Melina." (ER) · "Welcome to the bonfire, Unkindled One." (DS3, Fire Keeper)
- Interjection before content: `Ah,` / `Oh,` / `Ahh...` / `Hm?` / `Well, well?` "Ah, hello! You don't look Hollow, far from it!" (DS1, Solaire) · "Hm? Wondering what's inside the treasure chest?" (ER, Patches) · "Ah, you. What is it?" (ER, Gideon) · "Ah-hah, you must be the new hunter." (BB, Gehrman)
- Reading the player's face as the greeting. "Oh, your face! You're practically Hollow." (DS1, Crestfallen) · "Your eyes... The eyes of a wolf who has failed in his duties." (Sekiro, Sculptor) · "You're a Tarnished, I can see it." (ER, Kalé)

## Cadence

- Laughter is its own terminal line, never mid-sentence. "Hah hah hah!" (Solaire) · "Hah hah hah hah…" with trailing ellipsis = bitter (Crestfallen) · "Ha ha ha..." / "He he he he he..." (Patches) · "Ah hah hah ha!" (Micolash)
- Minimal responses as whole lines: `I see.` / `Very well.` / `Then it's settled.` / `...Well.` / `Good.` "Then it's settled." (Melina) · "Very well. As your senior, I bid you welcome." (Gideon) · "...Well. / A lowly Tarnished, / playing as a lord." (Godrick) · Sekiro densest: "...I see." / "Good." / "We're done here."
- Ellipsis about one per three lines. Leading `...` = reluctance; trailing `...` = decay. "My purpose…was long ago lost." (Melina) · "...It's the same old story, everywhere I go. Ah, to hell with it all." (Patches)
- Rhetorical question, then self-answer. "Do you find that strange? Well, you should!" (Solaire) · "Does he really exist? Well, go and find out for yourself." (Crestfallen) · "Dear, oh dear, what was it? The hunt, the blood, or the horrible dream? Oh, it doesn't matter." (Gehrman)

## Warnings and hints

- Fact, then consequence. The player draws the imperative. "One of the bells is up above in the Undead Church, but the lift is broken." (Crestfallen) · "The Erdtree wards off all who deign approach. / We are... we are all forsaken." (Morgott) · "If you hesitate you'll be swept away... and lose the battle." (Isshin)
- Off-screen proper nouns, never glossed. "Oh, Laurence... Master Willem... Somebody help me..." (Gehrman) · "Long ago, I was told of a remedician who resides in New Londo." (Crestfallen) · "Has the little Lord Ludleth spoken to thee of any…curious matters?" (Fire Keeper)
- Hedge on own knowledge. "But now it is all that guides you. Or so I hear." (Melina) · "They say the Mortal Blade cannot be drawn. ... It's just hearsay." (Isshin)

## Register

- thee/thou is a caste marker. Keepers, demigods, ancient lords use it; Tarnished, merchants, hunters speak modern colloquial. "I tend to the flame and tend to thee." (Fire Keeper) · "Thy kind are all of a piece." (Morgott) · "I command thee, kneel!" (Godrick) versus "Cripes, are you dense, boy?" (Patches) · "Is that all you were, mate?" (Kalé). One speaker, one register.
- Self-introduction is period-broken: `I am X. Y of Z.` then a boast or offer. "I am Malenia. Blade of Miquella. / And I have never known defeat." · "I'm Patches. Patches the Untethered." · "I am Kalé. Purveyor of fine goods." · "I am Solaire of Astora, an adherent of the Lord of Sunlight."
- Boss taunt = roll-call, then epitaph. "Godrick the Golden. / The twin prodigies, Miquella and Malenia. / General Radahn. ... Wilful traitors, all." → "Have it writ upon thy meagre grave: / Felled by King Morgott!" On the player's death the intro is repeated verbatim (Malenia).
- Farewell is one clause. "Farewell, Ashen One. May the flames guide thee." (DS3 FK) · "Go now." (Sculptor) · "Fear the blood." (Gehrman) · "Good-bye. Nice to do business." (Kalé) · "Don't be a stranger, eh?" (Patches) · "Hesitate, and you lose." (Isshin)
- Dying line = trailing address to an absent name. "O, dearest Miquella, my brother... / I'm sorry. I finally met my match." (Malenia) · "My…my sun…" (Solaire) · "Is this...how it ends? / I'll never find..." (Kalé)

## Archetype table

| Archetype | Address | Tic | Register |
|---|---|---|---|
| Guide, keeper (Melina, Fire Keeper) | `Ashen One`, `Traveller` | `Or so I hear`, `Then it's settled` | thee/thou (FK); formal modern (Melina) |
| Jolly knight (Solaire) | `hello there` | `Hah hah hah!`, `jolly co-operation` | earnest modern |
| Trickster (Patches) | `friend`, `boy` | `water under the bridge`, `Ha ha ha...` | cockney colloquial |
| Merchant (Kalé) | `customer`, `mate` | `Care to purchase anything?` | polite salesman |
| Scholar (Gideon, Micolash) | `newcomer` | roll-calls of names; `To be all-knowing.` | clipped superior; feverish |
| Crestfallen | `you must be a new arrival` | `Hah hah hah hah…` after every bad news | sardonic |
| Old hunter (Gehrman) | `Good hunter` | `Oh, Laurence...` | weary, plain |
| Demigod boss | `Tarnished`, `thou'rt` | roll-call → epitaph | thee/thou, `writ`, `deign` |
| Sekiro (Sculptor, Isshin) | `Sekiro`, none | `...I see.` `Need something?` `Go now.` | terse, no archaism |

## Player messages

Grammar: `TEMPLATE(word)` + optional `CONJ TEMPLATE(word)`. Words come from fixed lists (enemy, dog, liar, weak foe, hidden path, edge, fort, night, finger, hole, chest, grace, message…), never free text.

Elden Ring templates: `**** ahead` · `No **** ahead` · `**** required ahead` · `Be wary of ****` · `Try ****` · `Likely ****` · `First off, ****` · `Seek ****` · `Still no ****...` · `Why is it always ****?` · `If only I had a ****...` · `Didn't expect ****...` · `Visions of ****...` · `Could this be a ****?` · `Time for ****` · `****, O ****` · `Behold, ****!` · `Offer ****` · `Praise the ****!` · `Let there be ****` · `Ahh, ****...` · `****!` · `****?` · `****...`

Conjunctions: `and then` · `or` · `but` · `therefore` · `in short` · `except` · `by the way` · `so to speak` · `all the more` · `,`

DS3 adds `only`. DS1 has no conjunctions and era words (`chest`, `fatty`, `beanpole`, `liar`, `Need ****`, `I did it!`).

KR templates (official): 「이 너머, * 있다 / 없다 / 필요하다 / 주의해라 / 유효하다」 · 「아마도 *」 · 「우선 *」 · 「목표는 *」 · 「*, 아직인가...」 · 「역시 *인가...」 · 「*만 있었다면...」 · 「*일 줄이야...」 · 「*의 예감...」 · 「*인 것 같지?」 · 「*의 시간이다」 · 「* 오오 *」 · 「*, 바라볼지라」 · 「* 바쳐라」 · 「* 만세!」 · 「* 있으라!」 · 「아아, *...」 · 「*!」 · 「*?」 · 「*...」
KR words (sampler): 잔챙이 · 강적 · 보스 · 개 · 늑대 · 게 · 벌레 · 거짓말쟁이 · 비겁자 · 뚱뚱한 녀석 · 보물상자 · 손가락 · 구멍 · 축복 · 메시지 · 숨겨진 길 · 막다른 길 · 절벽 · 요새 · 밤 · 구석 · 점프 · 패리 · 구르기 · 아침 · 절경 · 스태미나 부족 · 잘 했다 · 그럴 자격 없다 · 각오는 됐나?
KR conjunctions: 그리고 · 혹은 · 하지만 · 그러므로 · 요컨대 · 그건 그렇고 · 「,」

Idioms: `try finger but hole` · `dog` for any animal (`Dog ahead` at a turtle) · `fort, night` · `liar ahead` / `be wary of liar` under a lie · `hidden path ahead` / `try jumping` at a cliff = lie · `didn't expect weak foe...` after a hard boss · `visions of dog...` at ladders · `time for jumping` on lethal drops · `edge, edge, edge` · `O, you don't have the right` at locked doors · `praise the message` · `try tongue but hole`, `need head`, `amazing chest ahead` (DS ancestors) · `Elden Ring, O Elden Ring`

What makes a message funny in-canon: the template is obeyed exactly but the noun is wrong (deadpan literalism); the lie sits in a trusted format; understatement after trauma; comma-repetition for rhythm. Two clauses, never an explanation.

## Tells of a generic imitation

1. thee/thou for everyone; merchants say `mate`, `cripes`, `eh?`.
2. Lore explained or advice listed; real NPCs state one fact and stop.
3. No interjection or vocative; starts mid-thought like prose.
4. Laugh mid-sentence, or none.
5. Self-intro as one flowing sentence.
6. Proper nouns explained.
7. Ornate farewell.
8. Message over two clauses, free vocabulary, or a joke explained.
