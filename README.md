# exam-timer

*A truly bespoke, hand-crafted timepiece for use during written exams.*

Take a look at [the demo](https://ghpages.noahdoersing.com/exam-timer/examtimer.html) (press <kbd>space</kbd> to start the timer) or continue reading to find out what this is all about.

<img src="photo.jpg" alt="">


## Why?

* Not every lecture hall has a wall clock.
* A faint projector hum is **less distracting for your students** than the sound of writing the current time on a chalkboard every 10 minutes.
* Having relevant organizational matters always visible will **reduce the number of questions**.
* Exams for large courses are commonly written in multiple locations at the same time. This tool helps **communicate the same guidelines everywhere**.
* This tool is **easy to configure**, has **no dependencies** and **runs in your browser**.


## Usage

1. Take a look at the source code of `examtimer.html`.
    * Configure the **exam duration** in line 8. If necessary, you can modify the various timer labels in the following lines.
    * Around line 75, in `<section class="infos">`, replace the placeholder data with whatever **organizational matters** might be relevant for your specific exam. To **control during which phases of the exam an element** is shown, use the following four classes:

        ```
        <li class="before">Shown before the exam begins.</li>
        <li class="during">Shown during the initial part of the exam.</li>
        <li class="homestretch">Shown during the final 10 minutes.</li>
        <li class="after">Shown after the timer hits 0.</li>
        ```

        You can combine these classes arbitrarily:

        ```
        <li class="before during homestretch">Visible until the exam is over.</li>
        ```

        Elements without any of these four classes will always be shown.
2. Before your students arrive, **open `examtimer.html` in a browser**.
    * Disable your computer's sleep mode (or set the sleep timer to a sufficiently large value). If there's a separate screen sleep mode or screen saver, disable that too.
    * If you're running software that might show some sort of notification or update dialog (looking at you, Java), it's best to keep it closed during the exam.
    * Press <kbd>f</kbd> to enter fullscreen mode.
    * If necessary, adjust the text size to your liking using your browser's built-in tools (commonly <kbd>ctrl/⌘</kbd><kbd>+/-</kbd>).
3. Once everything's ready to go, **press the <kbd>space</kbd> bar** to start the timer.
    * You can **pause (and resume) the timer** by again pressing the <kbd>space</kbd> bar.
    * A Unix timestamp corresponding to the start time plus the total pause duration will be appended to the URL, so if your computer happens to crash, you can resume the timer via your browser history.


## Notes

* The first version of this timer (see commit `771a822`) was successfully used during the "Datenbanksysteme I" exam at the University of Tübingen in the 2017/18 winter semester.
* The improved version was in use during the "Informatik 1" (CS101 equivalent) exams at the University of Tübingen in the 2018/19 winter semester, and during the "Datenbanksysteme I" exam a year later.
* A hat tip to Tim Beckmann, whose [examclock](https://github.com/elogy/examclock) I've considerd forking after building the first version of this timer and before extending it to more-or-less match his clock's feature set. (Klausu(h)r ist der *beste* Wortwitz!)
