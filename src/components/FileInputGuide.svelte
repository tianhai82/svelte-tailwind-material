<script>
  import Button from "../widgets/Button.svelte";
  import Checkbox from "../widgets/Checkbox.svelte";
  import Input from "../widgets/Input.svelte";
  import FileInput from "../widgets/FileInput.svelte";

  let label = "Select a file";
  let accept = ".docx,.txt,.js,.json,.readme";
  let clearable = false;
  let disabled = false;

  let borderColor = "border-gray-700";
  let labelColor = "text-gray-700";
  let helperText = "Click the input box to select a file";
  let helperTextColor = "text-red-600";
  let outlined = false;
  let icon = "description";
  let hideDetails = false;
  let multiple = false;
  let value = null;

  let showCode = false;
</script>

<h2 class="text-xl ml-4 font-semibold my-6">File Input</h2>

<div class="bg-gray-200 rounded my-4 px-4 table w-full">
  <h3 class="text-lg font-bold ml-3 mt-5 mb-3">Properties</h3>
  <div class="table-row font-bold">
    <div class="table-cell py-3 px-3 border-b border-gray-400">Prop</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">Description</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">Type</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">Default</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">label</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The label text of the input box.
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">''</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">accept</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      Specify what file types the user can pick from the file input dialog box.
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">''</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">multiple</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      Whether multiple files can be selected
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">boolean</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">false</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">value</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The FileList selected by the user
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">''</div>
  </div>

  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">borderColor</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The border color of the input box. Accepts valid Tailwindcss border color
      class
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      border-gray-700
    </div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">labelColor</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The color of the label text. Accepts valid Tailwindcss text color class
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      text-gray-700
    </div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">helperText</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The helper text underneath the input box.
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">''</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      helperTextColor
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The color of the helper text underneath the input box. Accepts Tailwindcss
      text color class
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">''</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">outlined</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      Transformed this into a outlined input box.
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">boolean</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">false</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">icon</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      The icon to display on the right of the input box. <br /> Accepts a material
      icon from this list <a
        class="text-blue-600"
        href="https://material.io/resources/icons/?style=baseline">https://material.io/resources/icons/?style=baseline</a>
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">string</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">''</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">clearable</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      Includes a clear button when 'clearable' is true
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">boolean</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">false</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">disabled</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      Disables input box.
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">boolean</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">false</div>
  </div>
  <div class="table-row">
    <div class="table-cell py-3 px-3 border-b border-gray-400">hideDetails</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">
      Hides helper text.
    </div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">boolean</div>
    <div class="table-cell py-3 px-3 border-b border-gray-400">false</div>
  </div>
</div>

<div class="bg-gray-200 rounded p-4 w-full">
  <h3 class="mx-2 mb-2 flex justify-between">
    <div class="text-lg font-bold">Demo</div>
    <Checkbox bind:checked={showCode}>Show Code</Checkbox>
  </h3>
  <div class="my-2">
    <FileInput
      {label}
      {accept}
      {multiple}
      bind:value
      {borderColor}
      {labelColor}
      {helperText}
      {helperTextColor}
      {outlined}
      {icon}
      {clearable}
      {disabled}
      {hideDetails} />
  </div>

  <div class="border border-gray-500 rounded px-3 py-4 w-full">
    <div class="w-full flex flex-row flex-wrap">
      <div class="px-4">
        <Checkbox label="multiple" bind:checked={multiple} />
      </div>
      <div class="px-4">
        <Checkbox label="outlined" bind:checked={outlined} />
      </div>
      <div class="px-4">
        <Checkbox label="clearable" bind:checked={clearable} />
      </div>
      <div class="px-4">
        <Checkbox label="disabled" bind:checked={disabled} />
      </div>
      <div class="px-4">
        <Checkbox label="hideDetails" bind:checked={hideDetails} />
      </div>
    </div>
    <div class="w-full flex flex-row flex-wrap">
      <div class="px-4 pb-2">
        <Input hideDetails outlined label="label" bind:value={label} />
      </div>
      <div class="px-4 pb-2">
        <Input hideDetails outlined label="accept" bind:value={accept} />
      </div>
      <div class="px-4 pb-2">
        <Input hideDetails outlined label="value" bind:value />
      </div>
      <div class="px-4 pb-2">
        <Input hideDetails outlined label="icon" bind:value={icon} />
      </div>
      <div class="px-4 pb-2">
        <Input
          hideDetails
          outlined
          label="borderColor"
          bind:value={borderColor} />
      </div>
      <div class="px-4 pb-2">
        <Input
          hideDetails
          outlined
          label="labelColor"
          bind:value={labelColor} />
      </div>
      <div class="px-4 pb-2">
        <Input
          hideDetails
          outlined
          label="helperText"
          bind:value={helperText} />
      </div>
      <div class="px-4 pb-2">
        <Input
          hideDetails
          outlined
          label="helperTextColor"
          bind:value={helperTextColor} />
      </div>
    </div>
  </div>
</div>

<pre
  class:hidden={!showCode}
  class="my-2 bg-gray-200 rounded p-5 font-light">
{`<FileInput
  {label}
  {accept}
  {multiple}
  bind:value
  {borderColor}
  {labelColor}
  {helperText}
  {helperTextColor}
  {outlined}
  {icon}
  {clearable}
  {disabled}
  {hideDetails} />`}
</pre>
