<!-- TODO: Create the small heading subtitle from metadata. See #31. -->
# {{ entry.electrochemical_system.electrodes.working_electrode.material }}({{ entry.electrochemical_system.electrodes.working_electrode.crystallographic_orientation }}) <small>- {{ entry.electrochemical_system.electrolyte | render("components/electrolyte.md") }}</small>
<!-- TODO: Simplify the entry for electrode material, throughout the entire document: See #42. -->
<!-- TODO: Create text from metadata. See #31. -->
<!-- TODO: We should merge all our .bib files when building the pages and then create reference to original article from that .bib file. See #31. -->
A cyclic voltammogramm for 
{{ entry.electrochemical_system.electrodes.working_electrode.material }}
({{ entry.electrochemical_system.electrodes.working_electrode.crystallographic_orientation }}) 
recorded in 
{{ entry.electrochemical_system.electrolyte | render("components/electrolyte.md") }}
at a scan rate of 
{{ entry.figure_description.scan_rate | render }}
from Figure 
{{entry.source.figure }} 
in 
[N. Author *et al.*, *Journal Name*, **Volume** (YEAR) Page, "TITLE"](https://doi.org/10.1039/C0CP01001D).

<!-- TODO: Show plots with original axis units, see #25. It would be great if we could toggle between SI and original units. See #31. -->
<!-- TODO: Properly format plots. They should probably be much bigger since they are nice to look at. See #31. -->
{{ entry.plot()._repr_html_() }}

{{ entry.plot('A / m^2')._repr_html_() }}

**Figure notes:**  
The figure shows {{ entry.figure_description.type }} data.
{% if entry.figure_description.comment %}
Note from the curator: {{ entry.figure_description.comment }}
{% endif %}
<details>
<summary>Click to expand complete figure metadata (yaml).</summary>

```yaml
{{ entry.figure_description.yaml }}
```
</details>

<!-- TODO: Make download link work, i.e., build .zip package and link to it here. See #31. -->
[Download datapackage with ID-XXXXXXXX](#TODO)

<!-- TODO: Style this section. See #31. -->
## Further information
**Preparation procedure**
{% if entry.electrochemical_system.electrodes.working_electrode.preparation_procedure is defined %}
The {{ entry.electrochemical_system.electrodes.working_electrode.material }}({{ entry.electrochemical_system.electrodes.working_electrode.crystallographic_orientation }}) electrode was prepared by:  
{{ entry.electrochemical_system.electrodes.working_electrode.preparation_procedure }}
{% else %}
Preparation procedure not available.
{% endif %}

`Content from the yaml file`

<!-- TODO: Insert all the metadata from the .yaml file in some collapsible form here. E.g., just the YAML file with syntax highlighting. See #31. -->
## Metdata
<details>
<summary>Click to expand metadata (yaml).</summary>

```yaml
{{ entry.electrochemical_system.yaml }}
```
</details>

----

<!-- TODO: Insert links to other data which are plotted in the same figure and/or even add a plot with all data from that figure. See #31 -->