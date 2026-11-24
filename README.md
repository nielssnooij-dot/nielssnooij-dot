## Niels Karel Snooij

I build small models that read DNA, and I measure them against the simplest
method that could give the same answer. Most of what I publish is the comparison,
not the model.

Everything below is at [**bioX**](https://github.com/bioxcompute) ·
[bioxcompute.com](https://bioxcompute.com) ·
[ORCID 0009-0001-3411-1062](https://orcid.org/0009-0001-3411-1062)

### What is running

**[EH14 X](https://github.com/bioxcompute/eh14x)** reads marker genes and
environmental DNA. 257 M parameters, served, access by request. It scores how
expected each base is, places a sequence no database has a name for, writes
detection probes, and tells a real read from a PCR artefact.

That last one is the only task where it beats the tool people actually use:
**0.9735 against 0.9442** for UCHIME in vsearch 2.32 on the same set, a
difference of 0.0293 with interval [0.0208, 0.0385]. At equal abundance, where
both methods see only the letters. In a real sample UCHIME also has the
abundance of every read and we do not model it, so this beats UCHIME on the
letters, which is a narrower claim than beating UCHIME.

### What is not running, and why that is here

A route that scored 0.3687 on human variant effect, below the 0.5 of guessing,
answers **410 Gone** instead of a number. It existed and it was taken away on
purpose. Two different models once answered on one name there, and while that
was true the weaker one undermined the model I actually stand behind.

Counting four-letter words still ties or beats my 257 M model on marine novelty
detection. Paired over taxa the difference is -0.024 [-0.076, +0.026], so the
sharper test says the same as the wider one: that measurement does not separate
the two. I publish the baseline so other people can hold me to it:

**[dark-taxa-novelty](https://github.com/bioxcompute/dark-taxa-novelty)** is
1,760 18S sequences with forty whole taxa held out, frozen at v1.0, and a 60-line
numpy baseline that four published DNA foundation models do not beat.

### How I measure

Always a stupid baseline beside the number, because a score with nothing to beat
is not a score. Whole groups held out, never random rows, and the interval on the
unit that was held out: resampling rows here comes out about 3.75 times too
narrow. The bar written down before the run, not after. And the floor measured
too, because a test that always finds something finds nothing.

The reports that disagreed with me are in the same folder as the ones that did
not. There is a floor that moved 6.5 points once I counted compounds instead of
database rows, and it moved against my own rule.

Nothing I have designed has been tested in a laboratory yet. When one is, the
result goes up either way.
