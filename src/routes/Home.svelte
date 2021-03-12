<script lang="ts">
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";
    import { writable } from "svelte/store";
    import Carousel from "@beyonk/svelte-carousel";
    const loaded = writable(sessionStorage.getItem("loaded") || "");
    loaded.subscribe((val) => sessionStorage.setItem("loaded", val));
    // loaded.set(0);
    onMount(() => {
        loaded.set(1);
    });
    const delaysConfig = [
        500,
        1500,
        3000,
        4100,
        4200,
        4300,
        4400,
        8000,
        9000,
        13000,
        14000,
        18000,
        19000,
        23000,
        24000,
    ];
    let delays = [];
    for (let i = 0; i < delaysConfig.length; i++) {
        if (!$loaded) {
            delays[i] = { delay: delaysConfig[i], duration: 500 };
        } else {
            delays[i] = { delay: 0, duration: 0 };
        }
    }
    let carousel;
    if (!$loaded) {
        setTimeout(() => {
            carousel.pause();
        }, 0);
        setTimeout(() => {
            carousel.resume();
        }, 3000);
    }
    // function enter() {
    //     carousel.pause();
    // }
    // function leave() {
    //     carousel.resume();
    // }
</script>

<div>
    <p in:fade={delays[0]}>
        get your personal projects off of the ground <span in:fade={delays[1]}
            >with productabot</span
        >
    </p>
    <div in:fade={delays[2]}>
        <!-- {on:mouseenter={enter} on:mouseleave={leave}} -->
        <Carousel
            bind:this={carousel}
            autoplay={5000}
            duration={400}
            perPage={1}
            easing="ease"
        >
            <!-- <span class="control" slot="left-control" style="color:#ffffff">←</span> -->
            <div class="slide-content">
                <p in:fade={delays[2]}>
                    <header1>create projects</header1> to give each idea a tangible
                    home
                </p>
                <projects>
                    <project in:fade={delays[3]}>
                        <img
                            alt=""
                            src="https://files.productabot.com/test/place4pals.png"
                            class="projectSquare"
                        />
                        place4pals
                    </project>
                    <project in:fade={delays[3]}>
                        <img
                            alt=""
                            src="https://files.productabot.com/test/heythisischris.png"
                            class="projectSquare"
                        />
                        heythisischris
                    </project>
                    <project class="not-mobile" in:fade={delays[4]}>
                        <img
                            alt=""
                            src="https://files.productabot.com/test/christmas.png"
                            class="projectSquare"
                        />
                        christmas
                    </project>
                    <project class="not-mobile" in:fade={delays[5]}>
                        <img
                            alt=""
                            src="https://files.productabot.com/test/alexandria.png"
                            class="projectSquare"
                        />
                        alexandria & chris
                    </project>
                    <project class="not-mobile" in:fade={delays[6]}>
                        <projectAdd>+</projectAdd>
                    </project>
                </projects>
            </div>
            <div class="slide-content">
                <p in:fade={delays[7]}>
                    <header1>log your hours</header1> and see the effort you've put
                    in
                </p>
                <img
                    class="image"
                    in:fade={delays[8]}
                    alt=""
                    src="logyourhours.png"
                />
            </div>
            <div class="slide-content">
                <p in:fade={delays[9]}>
                    <header1>use kanban boards</header1> to keep track of tasks
                </p>
                <img
                    class="image"
                    in:fade={delays[10]}
                    alt=""
                    src="kanban.png"
                />
            </div>
            <div class="slide-content">
                <p in:fade={delays[11]}>
                    <header1>create docs</header1> to organize your thoughts
                </p>
                <img class="image" in:fade={delays[12]} alt="" src="docs.png" />
            </div>
            <div class="slide-content">
                <p in:fade={delays[13]}>
                    <header1>keep a journal</header1> that syncs across web, desktop,
                    & mobile
                </p>
                <img
                    class="image"
                    in:fade={delays[14]}
                    alt=""
                    src="journal.png"
                />
            </div>
            <!-- <span class="control" slot="right-control" style="color:#ffffff">→</span> -->
        </Carousel>
    </div>
    <div in:fade={delays[2]}>
        <p><header1>news</header1></p>
        <p>
            03/08/2021 @ 5:30pm est - launched the marketing website for
            productabot
        </p>
    </div>
</div>

<style>
    header1 {
        font-size: 30px;
        font-weight: bold;
    }
    projects {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-start;
    }
    project {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        font-size: 14px;
        margin-right: 40px;
        cursor: pointer;
        margin-top: 30px;
    }
    .projectSquare {
        width: 120px;
        height: 120px;
        border: 1px solid #ffffff;
        margin-bottom: 5px;
    }
    projectAdd {
        width: 120px;
        height: 120px;
        font-size: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    @media (max-width: 640px) {
        project {
            margin-top: 0px;
            margin-bottom: 40px;
        }
    }
</style>
