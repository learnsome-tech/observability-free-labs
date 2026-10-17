# m01l01-04 · A health check that says yes while work is failing

**Lesson:** [Observability Versus Monitoring](https://learnsome.tech/learn/observability-course/m01l01) (lesson 1.1, module 1: The Foundations Of Observability) · Free  
**Check:** Runs, not graded

## Goal

You can say what monitoring is good at, what observability adds, and why a green health check is not evidence that a service is working.

## Files

- [`starter/session-a-health-check-that-says-yes-while-work-is-f.sh`](starter/session-a-health-check-that-says-yes-while-work-is-f.sh): the listing from the lesson
- [`check.json`](check.json): how `./check` runs and checks this lab

## Steps

1. Go to the starter: `cd labs/m01l01/m01l01-04/starter`
2. Read `session-a-health-check-that-says-yes-while-work-is-f.sh`.
3. The session types these commands, in order:

   ```sh
   curl -s localhost:8000/healthz
   curl -s localhost:8000/nope
   curl -s localhost:8000/metrics | grep 404 | cut -d' ' -f1
   ```
4. Run it: `bash session-a-health-check-that-says-yes-while-work-is-f.sh`.
5. Check it from the repository root: `./check m01l01-04`.

## How to check

`./check m01l01-04` copies `starter/` into a scratch directory and runs `bash session-a-health-check-that-says-yes-while-work-is-f.sh` there, the way the site's lab sandbox does: that directory is the working directory and `HOME`, `LANG=C.UTF-8`, `TZ=UTC`, a limit of 10 seconds and 256 KiB of output per stream.

It runs without a pass or fail: what the listing prints in the lab sandbox differs from the output recorded for the lesson (it depends on the machine, the clock or the network), so the site runs it without a pass or fail. `./check` shows the output and the exit code.

---

[Open the lesson on LearnSome.tech](https://learnsome.tech/learn/observability-course/m01l01) · [All labs of this lesson](../README.md) · [Course README](../../../README.md)
