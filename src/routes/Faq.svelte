<script lang="ts">
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";
</script>

<div
    style="display:flex;flex-direction:column;justify-content:center;align-items:center;margin-top:10px;"
>
    <block>
        <p><header1>what is productabot?</header1></p>
        <p>it's an open-source and minimalist project management tool.</p>
    </block>
    <block>
        <p><header1>who made productabot?</header1></p>
        <p>
            chris aitken, you can check out my website
            <a
                style="text-decoration:underline"
                class="link"
                target="_blank"
                alt=""
                href="https://heythisischris.com/">here</a
            >.
        </p>
    </block>
    <block>
        <p><header1>why did you make productabot?</header1></p>
        <p>
            i tried looking for a better way to manage the time i put into my
            own projects, outside of work. it's hard holding yourself
            accountable, and the current productivity software offerings aren't
            well suited for solo users.
        </p>
        <ul>
            <li>basecamp is expensive</li>
            <li>airtable is way too modular</li>
            <li>JIRA is convuluted</li>
            <li>
                google workspace doesn't have a project-management framework
            </li>
        </ul>
        <p>
            so, instead of bouncing between basecamp, jira, airtable, and google
            workspace, i took matters into my own hands and made my own
            productivity app.
        </p>
    </block>
    <block>
        <p><header1>how can i help productabot?</header1></p>
        <p>
            shoot us an email at <a
                style="text-decoration:underline"
                class="link"
                target="_blank"
                alt=""
                href="mailto:support@productabot.com">support@productabot.com</a
            >
        </p>
    </block>
</div>

<style>
    block {
        width: 100%;
        max-width: 800px;
        margin-bottom: 0px;
    }
    header1 {
        font-size: 24px;
        font-weight: bold;
    }
</style>
