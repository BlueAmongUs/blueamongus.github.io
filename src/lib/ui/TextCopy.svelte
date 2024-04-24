<script lang="ts">
    import "$lib/styles/ui/TextCopy.scss"
    export let text: string;
    export let custom_success_message = "";

    function onCopy() {
        if (!navigator.clipboard) {
            alert("Sorry, cannot copy. Here is the text to copy \"" + text + "\"")
        }
        navigator.clipboard.writeText(text)
        .then(() => alert(custom_success_message || "Text successfully copied: \""+text+"\""))
        .catch(err => alert("Failed to copy text \""+text+"\", error: " + err))
    }

</script>

<button type="button" on:click={onCopy}>
    <slot/>
</button>