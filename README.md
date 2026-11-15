<h1 align="center">Kai Boyd</h1>

The rain usually decides my cycling layer before the map does. I’m Kai, a platform engineer based in Bristol, where I build and quietly maintain small tools that help geospatial data move more predictably through pipelines.

I work at Looking Heads, mostly at the seam between developer experience and data infrastructure. My favourite projects are not grand platforms; they are the narrow, useful utilities that save someone a bad afternoon: a boundary-file validator, a tile-preflight check, a retry policy that knows when to be patient.

---

## On the workbench

I tend to reach for **Go** when a job needs one steady binary, sensible concurrency, and an unmistakable CLI shape. **Python** still wins for exploratory geospatial work, especially when I am comparing projections, cleaning attributes, or asking whether a strange geometry is genuinely strange or merely inconvenient.

A current sketch is a small inspection toolkit for teams publishing open geographic data:

```text
fetch archive
   |
   v
verify file + projection
   |
   +-- odd geometry? -> report row id, don't guess
   |
   v
stage tiles + checksums
   |
   v
leave a readable note for the next maintainer
```

The tricky part has been resisting clever automatic fixes. If a polygon crosses itself or a coordinate reference system is missing, the tool should surface enough context for a human to decide. Silent correction feels convenient once and confusing for years.

```
go for: long-lived CLIs, concurrent fetchers, boring deploys
python for: shapely, pyproj, quick data questions
```

---

## Notes from the steep bits

I am learning to treat infrastructure logs like map contours: neither is the whole territory, but both show where things are likely to bend. A failed import can be a permissions issue, a malformed archive, or a dataset that quietly changed its schema at 3am.

Some open questions I keep circling:

- What belongs in a machine-readable validation report, and what is better as a plain sentence?
- How can cache keys stay understandable after a coordinate system changes?
- When does a workflow deserve a framework, and when is a well-named script kinder?

I do not have tidy answers yet. That uncertainty is usually where the better design starts.

---

## How I got here

My route into platform work was practical rather than polished. I used to make rough local maps for community projects, then kept being the person who wanted the shared file, upload script, and backup process to stop feeling fragile. Eventually I realised I cared just as much about the delivery path as the map itself.

Bristol keeps that habit alive. I cycle between harbourside, hills, and poorly signed roadworks, often noticing how infrastructure only becomes visible at its joins. Those rides feed short notes on maps, maintenance, open data, and the small interfaces people actually use.

> Good infrastructure, like a good cycle path, should let you keep moving without asking you to trust magic.

When I am off the bike, I am probably testing a smaller CLI flag, rereading a pull request for tone, or making a note that future maintainers are also people. 🚲
