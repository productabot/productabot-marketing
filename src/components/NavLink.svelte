<script>
    import { Link } from "svelte-routing";

    export let to = "";

    function getProps({ location, href, isPartiallyCurrent, isCurrent, noUnderline }) {
        const isActive =
            href === "/" ? isCurrent : isPartiallyCurrent || isCurrent;

        if (!noUnderline) {
            if (isActive) {
                return { class: "link active" };
            }
            return { class: "link" };
        } else {
            return {};
        }
    }
</script>

<Link {to} {getProps}>
    <slot />
</Link>
