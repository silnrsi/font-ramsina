sources/opentype/README.txt
==================

This file describes the fea source files included with the Ramsina
font family. This information should be distributed along with the 
Ramsina fonts and any derivative works.

These files are part of the Ramsina font family 
(https://github.com/silnrsi/font-ramsina) and are 
Copyright (c) SIL Global (https://www.sil.org/),
with Reserved Font Names "Ramsina" and "SIL".

This Font Software is licensed under the SIL Open Font License,
Version 1.1.

main.feax   Master source file for OpenType logic. Note this file utilizes
              FEA extensions provided by pysilfont.

Special alaph rules for U+0710
==========

Glyph 1: alaph-syriac.med2 (no descender)
Glyph 2: alaph-syriac.fina (descender)
Glyph 3: alaph-syriac.ccmp (comma shape)

The shape of this character varies, depending on context, the character that precedes it, and whether it has a diacritic or not.
These are conventions, and there is no documented hard rules of how the shape/form is rendered. We are currently following Paul
Bejan's practice, who seemed to have published the most manuscripts in printed form in Paris, more than 100 years ago.

1. 0715 SYRIAC LETTER DALATH (or 072A SYRIAC LETTER RISH) followed by 0710 SYRIAC LETTER ALAPH rendered as Glyph 1 (obligatory) 
2. 0720 SYRIAC LETTER LAMADH followed by 0710 SYRIAC LETTER ALAPH and NO diacritic on 0710 is rendered as Glyph 3. This is obligatory regardless of whether 0710 is in the middle or at the end of a word.
3. (removed) 0720 SYRIAC LETTER LAMADH followed by 0710 SYRIAC LETTER ALAPH and there is a diacritic on 0710, then 0710 is rendered as Glyph 1.
4. (removed) Any character, except 0720 SYRIAC LETTER LAMADH (which is covered by rules 2 & 3) followed by 0710 SYRIAC LETTER ALAPH and NO diacritic on 0710, then 0710 is rendered as Glyph 2. This is obligatory regardless of whether 0710 is in the middle or at the end of a word. 
5. (removed) Any character, except 0720 SYRIAC LETTER LAMADH (which is covered by rules 2 & 3), followed by 0710 SYRIAC LETTER ALAPH AND there is a diacritic on 0710, then 0710 is rendered as Glyph 1.
6. Glyph 3 is only used with 0720 SYRIAC LETTER LAMADH
7. All other contexts of 0710 SYRIAC LETTER ALAPH, follow the general rule of shaping, i.e. initial and final forms.

Notes: 
Rule 2 is the default if users don't use any diacritics at all (preceded by lamadh).
Rule 4 is the default if users don't use any diacritics at all (when not preceded by lamadh).

Changed alaph rules for U+0710
==========
Glyph 1: alaph-syriac.med2 and alaph-syriac.fin3 (no descender)
Glyph 2: alaph-syriac.fina (descender)
Glyph 3: alaph-syriac.ccmp (comma shape)

1)	 0715 SYRIAC LETTER DALATH followed by 0710 SYRIAC LETTER ALAPH 
OR
 072A SYRIAC LETTER RISH followed by  0710 SYRIAC LETTER ALAPH
Obligatory: 0710 is rendered as Glyph 1 
    Lookups: ltrMediOlaph (feature med2)
    Lookups: ltrFinaESyOlaph (feature fin3)
2)	0720 SYRIAC LETTER LAMADH followed by 0710 SYRIAC LETTER ALAPH and they end the word, then 0710 is rendered as Glyph 3. It can be a ligature with connecting and non-connecting form and be used universally.
    Lookups: LamAlaphLig_Alaph (called from LamAlaphLig) (feature ccmp)
    Lookups: AlaphChain (called from AlaphLigs) (feature ccmp)

6)	Glyph 3 is only used with 0720
7)	All other contexts of 0710, follow the general rule of shaping, i.e. initial, middle, and end forms. 
