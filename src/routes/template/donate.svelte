<script>
    import MediaQuery from "../MediaQuery.svelte";
</script>

<div class="donate-page">
    <!-- Optional leading content (e.g. a hero/image) passed in by the page -->
    <slot />

    <!-- Master grid: left content column flows under itself; cork board sits
         in the right column; the donations block spans full width at the bottom -->
    <div class="layout">
        <div class="left">
            <header class="intro">
                <h1>Donation for Temple Construction</h1>
                <p>
                    Your donation, regardless of size, is helpful in the
                    construction of the temple. Donors are encouraged to explore
                    the donation options below, and are more than welcome to
                    contribute in any way.
                </p>
            </header>

            <section class="committee-text">
                <h2>Temple Committee</h2>
                <p>
                    The construction and renovation works are overseen by the
                    Polikandy Kanthavanam Kalyanavelavaswamy Temple
                    Karunkattiruppani Committee. The committee guides every
                    stage of the project, from the mulasthanam and the mandapams
                    through to the parivara shrines and the eventual
                    kumbhabhishekam, and manages how devotees' contributions are
                    allocated. To reach devotees across the world, the committee
                    has also appointed overseas representatives in Switzerland,
                    the United Kingdom, and France. The official notices pinned
                    here set out the estimated scope of the works and the
                    appointed overseas representatives.
                </p>
            </section>

            <section class="card ways">
                <h2>Ways to Give</h2>
                <h3>Sponsor a Worker</h3>
                <p>
                    In order to maintain the elegance of our Sanathana Dharma
                    through a permanent home for Shanmukar, temple
                    administrators have made efforts to work with experienced
                    architects and builders. Sponsors are encouraged to
                    contribute towards new workers to build the temple at an
                    even quicker pace. Money contributed towards workers will be
                    used for the workers' food as well.
                </p>
                <h3>Sponsor Materials</h3>
                <p>
                    The traditional construction of the temple includes the use
                    of elegantly carved granite stones. While the granite temple
                    will be built to stand thousands of years, it is challenging
                    to cut through. Sponsors are encouraged to contribute
                    towards materials, such as: granite stones, construction
                    sand, construction tools, etc. For more detailed
                    information, please contact temple administration.
                </p>
            </section>
        </div>

        <!-- Cork board: notices stacked vertically as a tall column -->
        <div class="corkboard">
            <div class="committee-docs">
                <a
                    class="pinned pinned--left"
                    href="/committee1.webp"
                    target="_blank"
                    rel="noopener"
                >
                    <span class="pin" aria-hidden="true"></span>
                    <img
                        src="/committee1.webp"
                        alt="Temple committee notice outlining the estimated scope and cost of the construction works, with bank account details for donations"
                    />
                </a>
                <a
                    class="pinned pinned--right"
                    href="/committee2.webp"
                    target="_blank"
                    rel="noopener"
                >
                    <span class="pin" aria-hidden="true"></span>
                    <img
                        src="/committee2.webp"
                        alt="Temple committee notice announcing the appointed overseas representatives in Switzerland, London, and France with their contact numbers"
                    />
                </a>
            </div>
        </div>

        <!-- Donations: full-width block at the bottom -->
        <section class="card donations">
            <h2>Donations</h2>
            <p>
                Devotees from around the world are urged to donate. Your
                donation, regardless of size, preserves our culture of Sanathana
                Dharma through Shanmukar and will be appropriately allocated
                towards temple construction efforts.
            </p>
            <ul class="contact">
                <li class="label">Contact for Donation</li>
                <li>WhatsApp: +94 77-500-2162</li>
                <li>Mobile: +1 647-880-1416</li>
            </ul>

            <h3>Karunkattiruppani Bank Transfer</h3>
            <ul class="contact">
                <li>Bank: Hatton National Bank (HNB), Nelliady, Sri Lanka</li>
                <li>Account Number: 118020318297</li>
                <li>
                    Account Holders: K. Naveenthiran, T. Kannathasan,
                    N. Baskarasothy
                </li>
            </ul>

            <h3>Karunkattiruppani Committee Contacts</h3>
            <ul class="contact">
                <li>Phone: +94 21 226 6664</li>
                <li>Chairman: +94 77 500 2162</li>
                <li>Secretary: +94 77 222 9354</li>
                <li>Treasurer: +94 77 361 4377</li>
            </ul>

            <h3>Overseas Representatives</h3>
            <ul class="contact">
                <li>Switzerland &mdash; S. Vinayagalingam: +41 76 427 15 79</li>
                <li>London &mdash; S. Mayooran: +44 7490 187108</li>
                <li>France &mdash; M. Sreeskantharaja: +33 6 15 61 27 67</li>
            </ul>

            <h2 class="spaced">Inquiries</h2>
            <p>
                Please send any inquiries about donations, or any general
                inquiries about the temple and future events to:
            </p>
            <p class="email">info@kanthavanamtemple.com</p>
        </section>
    </div>
</div>

<style>
    .donate-page {
        box-sizing: border-box;
        width: min(1200px, 90%);
        margin: 0 auto;
        padding: 2rem 0 4rem;
        color: #ffd08e;
        display: flex;
        flex-direction: column;
        gap: 3rem;
    }

    .donate-page :global(*) {
        box-sizing: border-box;
    }

    h1 {
        font-size: clamp(2.5rem, 5vw, 4rem);
        line-height: 1.1;
        margin: 0 0 1rem;
    }

    h2 {
        font-size: clamp(1.8rem, 3vw, 2.75rem);
        line-height: 1.2;
        margin: 0 0 1rem;
    }

    h2.spaced {
        margin-top: 2.5rem;
    }

    h3 {
        font-size: clamp(1.2rem, 2vw, 1.6rem);
        line-height: 1.3;
        margin: 1.5rem 0 0.5rem;
    }

    p {
        font-size: 1.05rem;
        line-height: 1.6;
        margin: 0 0 1rem;
    }

    /* Master layout:
         row 1 -> left content column (col 1) + cork board (col 2)
         row 2 -> donations block spanning both columns */
    .layout {
        display: grid;
        grid-template-columns: 1fr auto;
        gap: 2.5rem 3rem;
        align-items: start;
    }

    .left {
        grid-column: 1;
        grid-row: 1;
        min-width: 0;
        display: flex;
        flex-direction: column;
        gap: 2rem;
    }

    .corkboard {
        grid-column: 2;
        grid-row: 1;
    }

    .donations {
        grid-column: 1 / -1;
        grid-row: 2;
    }

    .committee-text > p,
    .intro > p {
        max-width: 60ch;
    }

    .card {
        background: rgba(0, 0, 0, 0.18);
        border: 1px solid rgba(255, 208, 142, 0.35);
        border-radius: 16px;
        padding: 1.75rem 2rem;
    }

    .contact {
        list-style: none;
        padding: 0;
        margin: 1rem 0;
        font-size: 1.15rem;
        line-height: 1.9;
    }

    .contact .label {
        font-weight: 600;
        opacity: 0.85;
    }

    .email {
        font-size: 1.25rem;
        word-break: break-word;
    }

    /* Cork board holding the pinned notices (tall column on the right) */
    .corkboard {
        width: 420px;
        max-width: 100%;
        padding: 2.5rem 2rem;
        border-radius: 14px;
        /* layered gradients fake a cork grain over a warm tan base */
        background-color: #c19a5b;
        background-image:
            radial-gradient(
                circle at 15% 20%,
                rgba(120, 72, 20, 0.28) 0 2px,
                transparent 3px
            ),
            radial-gradient(
                circle at 70% 65%,
                rgba(120, 72, 20, 0.22) 0 2px,
                transparent 3px
            ),
            radial-gradient(
                circle at 40% 80%,
                rgba(90, 55, 15, 0.25) 0 1.5px,
                transparent 2.5px
            ),
            radial-gradient(
                circle at 85% 15%,
                rgba(150, 100, 40, 0.3) 0 2px,
                transparent 3px
            ),
            radial-gradient(
                circle at 55% 35%,
                rgba(90, 55, 15, 0.2) 0 1.5px,
                transparent 2.5px
            );
        background-size:
            90px 90px,
            120px 120px,
            70px 70px,
            140px 140px,
            60px 60px;
        border: 10px solid #6b4423;
        box-shadow:
            inset 0 0 60px rgba(60, 35, 10, 0.45),
            0 10px 30px rgba(0, 0, 0, 0.5);
    }

    .committee-docs {
        display: flex;
        flex-direction: column;
        gap: 2.5rem;
        align-items: center;
    }

    /* Each notice looks like a sheet of paper tacked to the board */
    .pinned {
        position: relative;
        display: block;
        width: 100%;
        max-width: 360px;
        padding: 12px 12px 28px;
        background: #fdfcf7;
        box-shadow: 0 6px 16px rgba(0, 0, 0, 0.4);
        transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .pinned--left {
        transform: rotate(-2.5deg);
    }

    .pinned--right {
        transform: rotate(2deg);
    }

    .pinned:hover {
        transform: rotate(0deg) scale(1.03);
        box-shadow: 0 12px 26px rgba(0, 0, 0, 0.5);
        z-index: 2;
    }

    .pinned img {
        display: block;
        width: 100%;
        height: auto;
    }

    /* Push-pin at the top of each sheet */
    .pin {
        position: absolute;
        top: -12px;
        left: 50%;
        width: 22px;
        height: 22px;
        transform: translateX(-50%);
        border-radius: 50%;
        background: radial-gradient(
            circle at 35% 30%,
            #ff7b7b 0%,
            #d12f2f 55%,
            #8f1b1b 100%
        );
        box-shadow:
            0 2px 4px rgba(0, 0, 0, 0.5),
            inset 1px 1px 2px rgba(255, 255, 255, 0.6);
    }

    .pin::after {
        content: "";
        position: absolute;
        top: 7px;
        left: 50%;
        width: 3px;
        height: 10px;
        transform: translateX(-50%);
        background: rgba(0, 0, 0, 0.35);
        border-radius: 2px;
    }
</style>

<MediaQuery query="(max-width: 1024px)" let:matches>
    {#if matches}
        <style>
            .layout {
                grid-template-columns: 1fr !important;
            }
            .left,
            .corkboard,
            .donations {
                grid-column: 1 !important;
                grid-row: auto !important;
            }
            .corkboard {
                width: 100% !important;
                max-width: 460px !important;
                margin: 0 auto !important;
            }
        </style>
    {/if}
</MediaQuery>
