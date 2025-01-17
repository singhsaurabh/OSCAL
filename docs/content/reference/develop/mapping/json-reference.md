---
title: "OSCAL Control Mapping Model Development Snapshot JSON Format Reference"
heading: "Control Mapping Model Development Snapshot JSON Format Reference"
weight: 20
generateanchors: false
sidenav:
  title: JSON Reference
toc:
  enabled: true
  headingselectors: "h1.toc1, h2.toc2, h3.toc3, h4.toc4, h5.toc5, h6.toc6"

---

The following is the JSON format reference for this [model](/concepts/layer/control/mapping/), which is organized hierarchically. Each entry represents the corresponding JSON property in the model's JSON format, and provides details about the semantics and use of the property. The [JSON Format Outline](../json-outline/) provides a streamlined, hierarchical representation of this model's JSON format which can be used along with this reference to better understand the JSON representation of this model.

<!-- DO NOT REMOVE. Generated text below -->
{{< rawhtml >}}
<div xmlns="http://www.w3.org/1999/xhtml" class="json-reference">
   <p><span class="usa-tag">JSON Base URI</span> <code>http://csrc.nist.gov/ns/oscal</code></p>
   <div class="remarks">The OSCAL Control mapping format can be used to describe how a collection of security
      controls and related control enhancements relate to another collection of controls.
      The root of the Control Catalog format is mapping-collection. </div>
   <div class="model-entry definition assembly">
      <div class="definition-header">
         <h1 id="/mapping-collection" class="toc1 name">mapping-collection</h1>
         <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping-collection">(global definition)</a></p>
         <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection">Switch to XML</a></div>
         <p class="formal-name">Mapping Collection</p>
      </div>
      <div class="body">
         <p class="description"><span class="usa-tag">Description</span> A collection of relationship-based control and/or control statement mappings.</p>
         <div class="remarks-group usa-prose">
            <details open="open">
               <summary class="subhead">Remarks</summary>
               <div class="remarks">
                  <p>A mapping collection affirmatively declares the relationships that exist between sets
                     of controls and/or control statements in a source and target. It is expected that
                     inferences can be made based on what is mapped; however, no inferences should be made
                     based on what is not mapped, since it is impossible to quantify how complete or granular
                     a given mapping is.</p>
               </div>
            </details>
         </div>
         <details class="properties" open="open">
            <summary>Properties (4)</summary>
            <div class="model-entry definition assembly">
               <div class="instance-header">
                  <h2 id="/mapping-collection/uuid" class="toc2 name">uuid</h2>
                  <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                  <p class="occurrence">[1]</p>
                  <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/@uuid">Switch to XML</a></div>
                  <p class="formal-name">Mapping Collection Universally Unique Identifier</p>
               </div>
               <div class="body">
                  <p class="description"><span class="usa-tag">Description</span> A globally unique identifier with cross-instance scope for this catalog instance.
                     This UUID should be changed when this document is revised.</p>
               </div>
            </div>
            <div class="model-entry definition assembly">
               <div class="instance-header">
                  <h2 id="/mapping-collection/metadata" class="toc2 name">metadata</h2>
                  <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping-collection/metadata">(global definition)</a></p>
                  <p class="occurrence">[1]</p>
                  <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata">Switch to XML</a></div>
                  <p class="formal-name">Document Metadata</p>
               </div>
               <div class="body">
                  <p class="description"><span class="usa-tag">Description</span> Provides information about the containing document, and defines concepts that are
                     shared across the document.</p>
                  <div class="remarks-group usa-prose">
                     <details open="open">
                        <summary class="subhead">Remarks</summary>
                        <div class="remarks">
                           <p>All OSCAL documents use the same metadata structure, that provides a consistent way
                              of expressing OSCAL document metadata across all OSCAL models. The metadata section
                              also includes declarations of individual objects (i.e., roles, location, parties)
                              that may be referenced within and across linked OSCAL documents.</p>
                           <p>The metadata in an OSCAL document has few required fields, representing only the bare
                              minimum data needed to differentiate one instance from another. Tools and users creating
                              OSCAL documents may choose to use any of the optional fields, as well as extension
                              mechanisms (e.g., properties, links) to go beyond this minimum to suit their use cases.</p>
                           <p>A publisher of OSCAL content can use the <code>published</code>, <code>last-modified</code>, and <code>version</code> fields to establish information about an individual in a sequence of successive revisions
                              of a given OSCAL-based publication. The metadata for a previous revision can be represented
                              as a <code>revision</code> within this object. Links may also be provided using the <code>predecessor-version</code> and <code>successor-version</code> link relations to provide for direct access to the related resource. These relations
                              can be provided as a link child of this object or as <code>link</code> within a given <code>revision</code>.</p>
                           <p>A <code>responsible-party</code> entry in this context refers to roles and parties that have responsibility relative
                              to the production, review, publication, and use of the containing document.</p>
                        </div>
                     </details>
                  </div>
                  <details class="constraints" open="open">
                     <summary>Constraints (14)</summary>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">role</code> an index <code>index-metadata-role-ids</code> shall list values returned by targets <code>role</code> using keys constructed of key field(s) <code>@id</code></p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">is unique</span>  for <code class="path">document-id</code>: any target value must be unique (i.e., occur only once)</p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">is unique</span>  for <code class="path">prop</code>: any target value must be unique (i.e., occur only once)</p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">.//prop</code> an index <code>index-metadata-property-uuid</code> shall list values returned by targets <code>.//prop</code> using keys constructed of key field(s) <code>@uuid</code></p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">is unique</span>  for <code class="path">link</code>: any target value must be unique (i.e., occur only once)</p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">role</code> an index <code>index-metadata-role-id</code> shall list values returned by targets <code>role</code> using keys constructed of key field(s) <code>@id</code></p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">location</code> an index <code>index-metadata-location-uuid</code> shall list values returned by targets <code>location</code> using keys constructed of key field(s) <code>@uuid</code></p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">party</code> an index <code>index-metadata-party-uuid</code> shall list values returned by targets <code>party</code> using keys constructed of key field(s) <code>@uuid</code></p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">party[@type='organization']</code> an index <code>index-metadata-party-organizations-uuid</code> shall list values returned by targets <code>party[@type='organization']</code> using keys constructed of key field(s) <code>@uuid</code></p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">is unique</span>  for <code class="path">responsible-party</code>: any target value must be unique (i.e., occur only once)</p>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">allowed values</span>  for <code class="path">responsible-party/@role-id</code></p>
                        <p>The value <b>may be locally defined</b>, or one of the following:</p>
                        <ul>
                           
                           <li><strong>creator</strong>: Indicates the person or organization that created this content.</li>
                           
                           <li><strong>prepared-by</strong>: Indicates the person or organization that prepared this content.</li>
                           
                           <li><strong>prepared-for</strong>: Indicates the person or organization for which this content was created.</li>
                           
                           <li><strong>content-approver</strong>: Indicates the person or organization responsible for all content represented in
                              the "document".</li>
                           
                           <li><strong>contact</strong>: Indicates the person or organization to contact for questions or support related
                              to this content.</li>
                           </ul>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">allowed value</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name</code></p>
                        <p>The value <b>must</b> be one of the following:</p>
                        <ul>
                           
                           <li><strong>keywords</strong>: The value identifies a comma-seperated listing of keywords associated with this
                              content. These keywords may be used as search terms for indexing and other applications.</li>
                           </ul>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">allowed values</span>  for <code class="path">link/@rel</code></p>
                        <p>The value <b>may be locally defined</b>, or one of the following:</p>
                        <ul>
                           
                           <li><strong>canonical</strong>: The link identifies the authoritative location for this resource. Defined by RFC
                              6596.</li>
                           
                           <li><strong>alternate</strong>: The link identifies an alternative location or format for this resource. Defined
                              by the HTML Living Standard</li>
                           
                           <li><strong>latest-version</strong>: This link identifies a resource containing the latest version in the version history.
                              Defined by RFC 5829.</li>
                           
                           <li><strong>predecessor-version</strong>: This link identifies a resource containing the predecessor version in the version
                              history. Defined by  RFC 5829.</li>
                           
                           <li><strong>successor-version</strong>: This link identifies a resource containing the predecessor version in the version
                              history. Defined by RFC 5829.</li>
                           </ul>
                     </div>
                     <div class="constraint">
                        <p><span class="usa-tag">is unique</span>  for <code class="path">document-id</code>: any target value must be unique (i.e., occur only once)</p>
                     </div>
                  </details>
                  <details class="properties" open="open">
                     <summary>Properties (15)</summary>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/title" class="toc3 name">title</h3>
                           <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/title">Switch to XML</a></div>
                           <p class="formal-name">Document Title</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A name given to the document, which may be used by a tool for display and navigation.</p>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/published" class="toc3 name">published</h3>
                           <p class="type"><a href="/reference/datatypes/#datetime-with-timezone">dateTime-with-timezone</a></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/published">Switch to XML</a></div>
                           <p class="formal-name">Publication Timestamp</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> The date and time the document was last made available.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>Typically, this date value will be machine-generated at the time the containing document
                                       is published.</p>
                                    <p>In some cases, an OSCAL document may be derived from some source material provided
                                       in a different format. In such a case, the <code>published</code> value should indicate when the OSCAL document instance was last published, not the
                                       source material.</p>
                                 </div>
                              </details>
                           </div>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/last-modified" class="toc3 name">last-modified</h3>
                           <p class="type"><a href="/reference/datatypes/#datetime-with-timezone">dateTime-with-timezone</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/last-modified">Switch to XML</a></div>
                           <p class="formal-name">Last Modified Timestamp</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> The date and time the document was last stored for later retrieval.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>This value represents the point in time when the OSCAL document was last updated,
                                       or at the point of creation the creation date. Typically, this date value will be
                                       machine generated at time of creation or modification. Ideally, this field will be
                                       managed by the editing tool or service used to make modifications when storing the
                                       modified document.</p>
                                    <p>The intent of the last modified timestamp is to distinguish between significant change
                                       milestones when the document may be accessed by multiple entities. This allows a given
                                       entity to differentiate between mutiple document states at specific points in time.
                                       It is possible to make multiple modifications to the document without storing these
                                       changes. In such a case, the last modified timestamp might not be updated until the
                                       document is finally stored.</p>
                                    <p>In some cases, an OSCAL document may be derived from some source material in a different
                                       format. In such a case, the <code>last-modified</code> value should indicate the last modification time of the OSCAL document instance,
                                       not the source material.</p>
                                 </div>
                              </details>
                           </div>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/version" class="toc3 name">version</h3>
                           <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/version">Switch to XML</a></div>
                           <p class="formal-name">Document Version</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> Used to distinguish a specific revision of an OSCAL document from other previous
                              and future versions.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>A version may be a release number, sequence number, date, or other identifier sufficient
                                       to distinguish between different document revisions.</p>
                                    <p>While not required, it is recommended that OSCAL content authors use <a href="https://semver.org/spec/v2.0.0.html">Semantic Versioning</a> as the version format. This allows for the easy identification of a version tree
                                       consisting of major, minor, and patch numbers.</p>
                                    <p>A version is typically set by the document owner or by the tool used to maintain the
                                       content.</p>
                                 </div>
                              </details>
                           </div>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/oscal-version" class="toc3 name">oscal-version</h3>
                           <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/oscal-version">Switch to XML</a></div>
                           <p class="formal-name">OSCAL Version</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> The OSCAL model version the document was authored against and will conform to as
                              valid.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>Indicates the version of the OSCAL model to which the document conforms, for example
                                       <q>1.1.0</q> or <q>1.0.0-milestone1</q>. That can be used as a hint for a tool indicating which version of the OSCAL XML
                                       or JSON schema to use for validation.</p>
                                    <p>The OSCAL version serves a different purpose from the document version and is used
                                       to represent a different concept. If both have the same value, this is coincidental.</p>
                                 </div>
                              </details>
                           </div>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/revisions" class="toc3 name">revisions</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Revision History Entry</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> An entry in a sequential list of revisions to the containing document, expected to
                              be in reverse chronological order (i.e. latest first).</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>While <code>published</code>, <code>last-modified</code>, and <code>oscal-version</code> are not required, values for these entries should be provided if the information
                                       is known. A <code>link</code> with a <code>rel</code> of <q>source</q> should be provided if the information is known.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="constraints" open="open">
                              <summary>Constraint (1)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed values</span>  for <code class="path">link/@rel</code></p>
                                 <p>The value <b>may be locally defined</b>, or one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>canonical</strong>: The link identifies the authoritative location for this resource. Defined by RFC
                                       6596.</li>
                                    
                                    <li><strong>alternate</strong>: The link identifies an alternative location or format for this resource. Defined
                                       by the HTML Living Standard</li>
                                    
                                    <li><strong>predecessor-version</strong>: This link identifies a resource containing the predecessor version in the version
                                       history. Defined by  RFC 5829.</li>
                                    
                                    <li><strong>successor-version</strong>: This link identifies a resource containing the predecessor version in the version
                                       history. Defined by RFC 5829.</li>
                                    
                                    <li><strong>version-history</strong>: This link identifies a resource containing the version history of this document.
                                       Defined by RFC 5829.</li>
                                    </ul>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (8)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/title" class="toc4 name">title</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/title">Switch to XML</a></div>
                                    <p class="formal-name">Document Title</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A name given to the document revision, which may be used by a tool for display and
                                       navigation.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/published" class="toc4 name">published</h4>
                                    <p class="type"><a href="/reference/datatypes/#datetime-with-timezone">dateTime-with-timezone</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/published">Switch to XML</a></div>
                                    <p class="formal-name">Publication Timestamp</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The date and time the document was last made available.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Typically, this date value will be machine-generated at the time the containing document
                                                is published.</p>
                                             <p>In some cases, an OSCAL document may be derived from some source material provided
                                                in a different format. In such a case, the <code>published</code> value should indicate when the OSCAL document instance was last published, not the
                                                source material.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/last-modified" class="toc4 name">last-modified</h4>
                                    <p class="type"><a href="/reference/datatypes/#datetime-with-timezone">dateTime-with-timezone</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/last-modified">Switch to XML</a></div>
                                    <p class="formal-name">Last Modified Timestamp</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The date and time the document was last stored for later retrieval.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This value represents the point in time when the OSCAL document was last updated,
                                                or at the point of creation the creation date. Typically, this date value will be
                                                machine generated at time of creation or modification. Ideally, this field will be
                                                managed by the editing tool or service used to make modifications when storing the
                                                modified document.</p>
                                             <p>The intent of the last modified timestamp is to distinguish between significant change
                                                milestones when the document may be accessed by multiple entities. This allows a given
                                                entity to differentiate between mutiple document states at specific points in time.
                                                It is possible to make multiple modifications to the document without storing these
                                                changes. In such a case, the last modified timestamp might not be updated until the
                                                document is finally stored.</p>
                                             <p>In some cases, an OSCAL document may be derived from some source material in a different
                                                format. In such a case, the <code>last-modified</code> value should indicate the last modification time of the OSCAL document instance,
                                                not the source material.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/version" class="toc4 name">version</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/version">Switch to XML</a></div>
                                    <p class="formal-name">Document Version</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Used to distinguish a specific revision of an OSCAL document from other previous
                                       and future versions.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>A version may be a release number, sequence number, date, or other identifier sufficient
                                                to distinguish between different document revisions.</p>
                                             <p>While not required, it is recommended that OSCAL content authors use <a href="https://semver.org/spec/v2.0.0.html">Semantic Versioning</a> as the version format. This allows for the easy identification of a version tree
                                                consisting of major, minor, and patch numbers.</p>
                                             <p>A version is typically set by the document owner or by the tool used to maintain the
                                                content.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/oscal-version" class="toc4 name">oscal-version</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/oscal-version">Switch to XML</a></div>
                                    <p class="formal-name">OSCAL Version</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The OSCAL model version the document was authored against and will conform to as
                                       valid.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Indicates the version of the OSCAL model to which the document conforms, for example
                                                <q>1.1.0</q> or <q>1.0.0-milestone1</q>. That can be used as a hint for a tool indicating which version of the OSCAL XML
                                                or JSON schema to use for validation.</p>
                                             <p>The OSCAL version serves a different purpose from the document version and is used
                                                to represent a different concept. If both have the same value, this is coincidental.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/revisions/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/links" class="toc4 name">links</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/revisions/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/links/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/links/rel" class="toc5 name">rel</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/links/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/revisions/links/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/revisions/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/revisions/revision/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/document-ids" class="toc3 name">document-ids</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/document-id">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                           <p class="occurrence">[0 to ∞]</p>
                           <p class="formal-name">Document Identifier</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A document identifier qualified by an identifier <code>scheme</code>.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>A document identifier provides a <a href="/concepts/identifier-use/#globally-unique">globally unique</a> identifier with a <a href="/concepts/identifier-use/#cross-instance">cross-instance</a> scope that is used for a group of documents that are to be treated as different versions,
                                       representations or digital surrogates of the same document.</p>
                                    <p>A document identifier provides an additional data point for identifying a document
                                       that can be assigned by a publisher or organization for purposes in a wider system,
                                       such as a digital object identifier (DOI) or a local content management system identifier.</p>
                                    <p>Use of a document identifier allows for document creators to associate sets of documents
                                       that are related in some way by the same <code>document-id</code>.</p>
                                    <p>An OSCAL document always has an implicit document identifier provided by the document's
                                       UUID, defined by the <code>uuid</code> on the top-level object. Having a default UUID-based identifier ensures all documents
                                       can be minimally identified when other document identifiers are not provided.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="properties" open="open">
                              <summary>Properties (2)</summary>
                              <div class="model-entry definition field">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/document-ids/scheme" class="toc4 name">scheme</h4>
                                    <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/document-id/@scheme">Switch to XML</a></div>
                                    <p class="formal-name">Document Identification Scheme</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Qualifies the kind of document identifier using a URI. If the scheme is not provided
                                       the value of the element will be interpreted as a string of characters.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed value</span></p>
                                          <p>The value <b>may be locally defined</b>, or the following:</p>
                                          <ul>
                                             
                                             <li><strong>http://www.doi.org/</strong>: A Digital Object Identifier (DOI); use is preferred, since this allows for retrieval
                                                of a full bibliographic record.</li>
                                             </ul>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition field">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/document-ids/identifier" class="toc4 name">identifier</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/document-id/_VALUE">Switch to XML</a></div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/props" class="toc3 name">props</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/props">(global definition)</a></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Property</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                              namespace qualified name/value pair.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>Properties permit the deployment and management of arbitrary controlled values, within
                                       OSCAL objects. A property can be included for any purpose useful to an application
                                       or implementation. Typically, properties will be used to sort, filter, select, order,
                                       and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                       an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                       lexical composition of properties may be constrained by external processes to ensure
                                       consistency.</p>
                                    <p>Property allows for associated remarks that describe why the specific property value
                                       was applied to the containing object, or the significance of the value in the context
                                       of the containing object.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="properties" open="open">
                              <summary>Properties (7)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/name" class="toc4 name">name</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/@name">Switch to XML</a></div>
                                    <p class="formal-name">Property Name</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                       characteristic, or quality of the property's containing object.</p>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed value</span></p>
                                          <p>The value <b>must</b> be one of the following:</p>
                                          <ul>
                                             
                                             
                                             <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                An optional class can be used to define the specific marking system used for the associated
                                                value.</li>
                                             </ul>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/uuid" class="toc4 name">uuid</h4>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/@uuid">Switch to XML</a></div>
                                    <p class="formal-name">Property Universally Unique Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/ns" class="toc4 name">ns</h4>
                                    <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/@ns">Switch to XML</a></div>
                                    <p class="formal-name">Property Namespace</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                       associate distinct semantics with the same name.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                             <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/value" class="toc4 name">value</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/@value">Switch to XML</a></div>
                                    <p class="formal-name">Property Value</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/class" class="toc4 name">class</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/@class">Switch to XML</a></div>
                                    <p class="formal-name">Property Class</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                             <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/group" class="toc4 name">group</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/@group">Switch to XML</a></div>
                                    <p class="formal-name">Property Group</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                property to associate it with one or more other properties in a given context.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/props/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/prop/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/links" class="toc3 name">links</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/link">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/links">(global definition)</a></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Link</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                              object.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                       a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                    <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                 </div>
                              </details>
                           </div>
                           <details class="constraints" open="open">
                              <summary>Constraints (3)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (4)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/links/href" class="toc4 name">href</h4>
                                    <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/link/@href">Switch to XML</a></div>
                                    <p class="formal-name">Hypertext Reference</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This value may be one of:</p>
                                             <ol>
                                                
                                                <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                
                                                <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                   document, or</li>
                                                
                                                <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                   (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                </ol>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/links/rel" class="toc4 name">rel</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/link/@rel">Switch to XML</a></div>
                                    <p class="formal-name">Link Relation Type</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                       can be an indicator of the link's purpose.</p>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed value</span></p>
                                          <p>The value <b>may be locally defined</b>, or the following:</p>
                                          <ul>
                                             
                                             <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                resource by UUID expressed as a bare URI fragment.</li>
                                             </ul>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/links/media-type" class="toc4 name">media-type</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/link/@media-type">Switch to XML</a></div>
                                    <p class="formal-name">Media Type</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                             <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                             <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                             <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                the initial content of the referenced resource.</p>
                                          </div>
                                          <div class="remarks">
                                             <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/links/text" class="toc4 name">text</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/link/text">Switch to XML</a></div>
                                    <p class="formal-name">Link Text</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                       a tool.</p>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/roles" class="toc3 name">roles</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Role</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> Defines a function, which might be assigned to a party in a specific situation.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>Permissible values to be determined closer to the application (e.g. by a receiving
                                       authority).</p>
                                    <p>OSCAL has defined a set of standardized roles for consistent use in OSCAL documents.
                                       This allows tools consuming OSCAL content to infer specific semantics when these roles
                                       are used. These roles are documented in the specific contexts of their use (e.g.,
                                       responsible-party, responsible-role). When using such a role, it is necessary to define
                                       these roles in this list, which will then allow such a role to be referenced.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="properties" open="open">
                              <summary>Properties (7)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/id" class="toc4 name">id</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/@id">Switch to XML</a></div>
                                    <p class="formal-name">Role Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A unique identifier for the role.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/title" class="toc4 name">title</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/title">Switch to XML</a></div>
                                    <p class="formal-name">Role Title</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A name given to the role, which may be used by a tool for display and navigation.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/short-name" class="toc4 name">short-name</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/short-name">Switch to XML</a></div>
                                    <p class="formal-name">Role Short Name</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A short common name, abbreviation, or acronym for the role.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/description" class="toc4 name">description</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/description">Switch to XML</a></div>
                                    <p class="formal-name">Role Description</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A summary of the role's purpose and associated responsibilities.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/roles/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/links" class="toc4 name">links</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/roles/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/links/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/links/rel" class="toc5 name">rel</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/links/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/roles/links/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/roles/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/role/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/locations" class="toc3 name">locations</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Location</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A physical point of presence, which may be associated with people, organizations,
                              or other concepts within the current or linked OSCAL document.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>An address might be sensitive in nature. In such cases a title, mailing address, email-address,
                                       and/or phone number may be used instead.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="constraints" open="open">
                              <summary>Constraints (5)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed value</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>type</strong>: Characterizes the kind of location.</li>
                                    </ul>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed value</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>data-center</strong>: A location that contains computing assets. A class can be used to indicate the sub-type
                                       of data-center as primary or alternate.</li>
                                    </ul>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed values</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>primary</strong>: The location is a data-center used for normal operations.</li>
                                    
                                    <li><strong>alternate</strong>: The location is a data-center used for fail-over or backup operations.</li>
                                    </ul>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">has cardinality</span>  for <code class="path">address</code> the cardinality of  <code>address</code> is constrained: <b>1</b>; maximum <b>unbounded</b>.</p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">has cardinality</span>  for <code class="path">title|address|email-address|telephone-number</code> the cardinality of  <code>title|address|email-address|telephone-number</code> is constrained: <b>1</b>; maximum <b>unbounded</b>.</p>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (9)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/uuid" class="toc4 name">uuid</h4>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/@uuid">Switch to XML</a></div>
                                    <p class="formal-name">Location Universally Unique Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A unique ID for the location, for reference.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/title" class="toc4 name">title</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/title">Switch to XML</a></div>
                                    <p class="formal-name">Location Title</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A name given to the location, which may be used by a tool for display and navigation.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/address" class="toc4 name">address</h4>
                                    <p class="type">object<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address">Switch to XML</a></div>
                                    <p class="formal-name">Address</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A postal address for the location.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The physical address of the location, which will provided for physical locations.
                                                Virtual locations can omit this data item.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (6)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/address/type" class="toc5 name">type</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address/@type">Switch to XML</a></div>
                                             <p class="formal-name">Address Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the type of address.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed values</span></p>
                                                   <p>The value <b>may be locally defined</b>, or one of the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>home</strong>: A home address.</li>
                                                      
                                                      <li><strong>work</strong>: A work address.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/address/addr-lines" class="toc5 name">addr-lines</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address/addr-line">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 to ∞]</p>
                                             <p class="formal-name">Address line</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A single line of an address.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/address/city" class="toc5 name">city</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address/city">Switch to XML</a></div>
                                             <p class="formal-name">City</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> City, town or geographical region for the mailing address.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/address/state" class="toc5 name">state</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address/state">Switch to XML</a></div>
                                             <p class="formal-name">State</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> State, province or analogous geographical region for a mailing address.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/address/postal-code" class="toc5 name">postal-code</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address/postal-code">Switch to XML</a></div>
                                             <p class="formal-name">Postal Code</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Postal or ZIP code for mailing address.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/address/country" class="toc5 name">country</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/address/country">Switch to XML</a></div>
                                             <p class="formal-name">Country Code</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> The ISO 3166-1 alpha-2 country code for the mailing address.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>: a target (value) must match the regular expression '[A-Z]{2}'.</p>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/email-addresses" class="toc4 name">email-addresses</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/email-address">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#email">email</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Email Address</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An email address as defined by <a href="https://tools.ietf.org/html/rfc5322#section-3.4.1">RFC 5322 Section 3.4.1</a>.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>A contact email associated with the location.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/telephone-numbers" class="toc4 name">telephone-numbers</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/telephone-number">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Telephone Number</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A telephone service number as defined by <a href="https://www.itu.int/rec/T-REC-E.164-201011-I/en">ITU-T E.164</a>.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>A phone number used to contact the location.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>: a target (value) must match the regular expression '^[0-9]{3}[0-9]{1,12}$'.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (2)</summary>
                                       <div class="model-entry definition field">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/telephone-numbers/type" class="toc5 name">type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/telephone-number/@type">Switch to XML</a></div>
                                             <p class="formal-name">type flag</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the type of phone number.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed values</span></p>
                                                   <p>The value <b>may be locally defined</b>, or one of the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>home</strong>: A home phone number.</li>
                                                      
                                                      <li><strong>office</strong>: An office phone number.</li>
                                                      
                                                      <li><strong>mobile</strong>: A mobile phone number.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition field">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/telephone-numbers/number" class="toc5 name">number</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/telephone-number/_VALUE">Switch to XML</a></div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/urls" class="toc4 name">urls</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/url">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Location URL</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The uniform resource locator (URL) for a web site or other resource associated with
                                       the location.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This data field is deprecated in favor of using a link with an appropriate relationship.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/locations/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/links" class="toc4 name">links</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/locations/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/links/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/links/rel" class="toc5 name">rel</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/links/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/locations/links/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/locations/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/location/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/parties" class="toc3 name">parties</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Party</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> An organization or person, which may be associated with roles or other concepts within
                              the current or linked OSCAL document.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>A party can be optionally associated with either an address or a location. While providing
                                       a meaningful location for a party is desired, there are some cases where it might
                                       not be possible to provide an exact location or even any location.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="constraints" open="open">
                              <summary>Constraint (1)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed values</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>mail-stop</strong>: A mail stop associated with the party.</li>
                                    
                                    <li><strong>office</strong>: The name or number of the party's office.</li>
                                    
                                    <li><strong>job-title</strong>: The formal job title of a person.</li>
                                    </ul>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (12)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/uuid" class="toc4 name">uuid</h4>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/@uuid">Switch to XML</a></div>
                                    <p class="formal-name">Party Universally Unique Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A unique identifier for the party.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/type" class="toc4 name">type</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/@type">Switch to XML</a></div>
                                    <p class="formal-name">Party Type</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A category describing the kind of party the object describes.</p>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed values</span></p>
                                          <p>The value <b>must</b> be one of the following:</p>
                                          <ul>
                                             
                                             <li><strong>person</strong>: A human being regarded as an individual.</li>
                                             
                                             <li><strong>organization</strong>: An organized group of one or more person individuals with a specific purpose.</li>
                                             </ul>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/name" class="toc4 name">name</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/name">Switch to XML</a></div>
                                    <p class="formal-name">Party Name</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The full name of the party. This is typically the legal name associated with the
                                       party.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/short-name" class="toc4 name">short-name</h4>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/short-name">Switch to XML</a></div>
                                    <p class="formal-name">Party Short Name</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A short common name, abbreviation, or acronym for the party.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/external-ids" class="toc4 name">external-ids</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/external-id">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Party External Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An identifier for a person or organization using a designated scheme. e.g. an Open
                                       Researcher and Contributor ID (ORCID).</p>
                                    <details class="properties" open="open">
                                       <summary>Properties (2)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/external-ids/scheme" class="toc5 name">scheme</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/external-id/@scheme">Switch to XML</a></div>
                                             <p class="formal-name">External Identifier Schema</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the type of external identifier.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>http://orcid.org/</strong>: The identifier is Open Researcher and Contributor ID (ORCID).</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/external-ids/id" class="toc5 name">id</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/external-id/_VALUE">Switch to XML</a></div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/parties/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/links" class="toc4 name">links</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/parties/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/links/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/links/rel" class="toc5 name">rel</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/links/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/links/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/email-addresses" class="toc4 name">email-addresses</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/email-address">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#email">email</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Email Address</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An email address as defined by <a href="https://tools.ietf.org/html/rfc5322#section-3.4.1">RFC 5322 Section 3.4.1</a>.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This is a contact email associated with the party.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/telephone-numbers" class="toc4 name">telephone-numbers</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/telephone-number">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Telephone Number</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A telephone service number as defined by <a href="https://www.itu.int/rec/T-REC-E.164-201011-I/en">ITU-T E.164</a>.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>A phone number used to contact the party.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>: a target (value) must match the regular expression '^[0-9]{3}[0-9]{1,12}$'.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (2)</summary>
                                       <div class="model-entry definition field">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/telephone-numbers/type" class="toc5 name">type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/telephone-number/@type">Switch to XML</a></div>
                                             <p class="formal-name">type flag</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the type of phone number.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed values</span></p>
                                                   <p>The value <b>may be locally defined</b>, or one of the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>home</strong>: A home phone number.</li>
                                                      
                                                      <li><strong>office</strong>: An office phone number.</li>
                                                      
                                                      <li><strong>mobile</strong>: A mobile phone number.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition field">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/parties/telephone-numbers/number" class="toc5 name">number</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/telephone-number/_VALUE">Switch to XML</a></div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="choice">
                                 <p>A choice:</p>
                                 <div class="model-entry definition assembly">
                                    <div class="instance-header">
                                       <h4 id="/mapping-collection/metadata/parties/addresses" class="toc4 name">addresses</h4>
                                       <p class="type">array<br /></p>
                                       <p class="occurrence">[0 or 1]</p>
                                       <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address">Switch to XML</a></div>
                                    </div>
                                    <div class="array-header">
                                       <p class="array-member">(array member)</p>
                                       <p class="type">object<br /></p>
                                       <p class="occurrence">[1 to ∞]</p>
                                       <p class="formal-name">Address</p>
                                    </div>
                                    <div class="body">
                                       <p class="description"><span class="usa-tag">Description</span> A postal address for the location.</p>
                                       <details class="properties" open="open">
                                          <summary>Properties (6)</summary>
                                          <div class="model-entry definition assembly">
                                             <div class="instance-header">
                                                <h5 id="/mapping-collection/metadata/parties/addresses/type" class="toc5 name">type</h5>
                                                <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                <p class="occurrence">[0 or 1]</p>
                                                <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address/@type">Switch to XML</a></div>
                                                <p class="formal-name">Address Type</p>
                                             </div>
                                             <div class="body">
                                                <p class="description"><span class="usa-tag">Description</span> Indicates the type of address.</p>
                                                <details class="constraints" open="open">
                                                   <summary>Constraint (1)</summary>
                                                   <div class="constraint">
                                                      <p><span class="usa-tag">allowed values</span></p>
                                                      <p>The value <b>may be locally defined</b>, or one of the following:</p>
                                                      <ul>
                                                         
                                                         <li><strong>home</strong>: A home address.</li>
                                                         
                                                         <li><strong>work</strong>: A work address.</li>
                                                         </ul>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                          <div class="model-entry definition assembly">
                                             <div class="instance-header">
                                                <h5 id="/mapping-collection/metadata/parties/addresses/addr-lines" class="toc5 name">addr-lines</h5>
                                                <p class="type">array<br /></p>
                                                <p class="occurrence">[0 or 1]</p>
                                                <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address/addr-line">Switch to XML</a></div>
                                             </div>
                                             <div class="array-header">
                                                <p class="array-member">(array member)</p>
                                                <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                <p class="occurrence">[0 to ∞]</p>
                                                <p class="formal-name">Address line</p>
                                             </div>
                                             <div class="body">
                                                <p class="description"><span class="usa-tag">Description</span> A single line of an address.</p>
                                             </div>
                                          </div>
                                          <div class="model-entry definition assembly">
                                             <div class="instance-header">
                                                <h5 id="/mapping-collection/metadata/parties/addresses/city" class="toc5 name">city</h5>
                                                <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                <p class="occurrence">[0 or 1]</p>
                                                <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address/city">Switch to XML</a></div>
                                                <p class="formal-name">City</p>
                                             </div>
                                             <div class="body">
                                                <p class="description"><span class="usa-tag">Description</span> City, town or geographical region for the mailing address.</p>
                                             </div>
                                          </div>
                                          <div class="model-entry definition assembly">
                                             <div class="instance-header">
                                                <h5 id="/mapping-collection/metadata/parties/addresses/state" class="toc5 name">state</h5>
                                                <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                <p class="occurrence">[0 or 1]</p>
                                                <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address/state">Switch to XML</a></div>
                                                <p class="formal-name">State</p>
                                             </div>
                                             <div class="body">
                                                <p class="description"><span class="usa-tag">Description</span> State, province or analogous geographical region for a mailing address.</p>
                                             </div>
                                          </div>
                                          <div class="model-entry definition assembly">
                                             <div class="instance-header">
                                                <h5 id="/mapping-collection/metadata/parties/addresses/postal-code" class="toc5 name">postal-code</h5>
                                                <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                <p class="occurrence">[0 or 1]</p>
                                                <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address/postal-code">Switch to XML</a></div>
                                                <p class="formal-name">Postal Code</p>
                                             </div>
                                             <div class="body">
                                                <p class="description"><span class="usa-tag">Description</span> Postal or ZIP code for mailing address.</p>
                                             </div>
                                          </div>
                                          <div class="model-entry definition assembly">
                                             <div class="instance-header">
                                                <h5 id="/mapping-collection/metadata/parties/addresses/country" class="toc5 name">country</h5>
                                                <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                <p class="occurrence">[0 or 1]</p>
                                                <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/address/country">Switch to XML</a></div>
                                                <p class="formal-name">Country Code</p>
                                             </div>
                                             <div class="body">
                                                <p class="description"><span class="usa-tag">Description</span> The ISO 3166-1 alpha-2 country code for the mailing address.</p>
                                                <details class="constraints" open="open">
                                                   <summary>Constraint (1)</summary>
                                                   <div class="constraint">
                                                      <p><span class="usa-tag">matches</span>: a target (value) must match the regular expression '[A-Z]{2}'.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                                 <div class="model-entry definition assembly">
                                    <div class="instance-header">
                                       <h4 id="/mapping-collection/metadata/parties/location-uuids" class="toc4 name">location-uuids</h4>
                                       <p class="type">array<br /></p>
                                       <p class="occurrence">[0 or 1]</p>
                                       <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/location-uuid">Switch to XML</a></div>
                                    </div>
                                    <div class="array-header">
                                       <p class="array-member">(array member)</p>
                                       <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                       <p class="occurrence">[0 to ∞]</p>
                                       <p class="formal-name">Location Universally Unique Identifier Reference</p>
                                    </div>
                                    <div class="body">
                                       <p class="description"><span class="usa-tag">Description</span> Reference to a location by UUID.</p>
                                       <details class="constraints" open="open">
                                          <summary>Constraint (1)</summary>
                                          <div class="constraint">
                                             <p><span class="usa-tag">index has key</span>this value must correspond to a listing in the index <code>index-metadata-location-uuid</code> using a key constructed of key field(s) <code>.</code></p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/member-of-organizations" class="toc4 name">member-of-organizations</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/member-of-organization">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Organizational Affiliation</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to another <code>party</code> by UUID, typically an organization, that this subject is associated with.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Since the reference target of an organizational affiliation must be another <code>party</code> (whether further qualified as person or organization) as inidcated by its <code>uuid</code>. As a <a href="/concepts/identifier-use/#machine-oriented">machine-oriented</a> identifier with uniqueness across document and trans-document scope, this <code>uuid</code> value is sufficient to reference the data item locally or globally across related
                                                documents, e.g., in an imported OSCAL instance. </p>
                                             <p>Parties of both the <code>person</code> or <code>organization</code> type can be associated with an organization using the <code>member-of-organization</code>.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>this value must correspond to a listing in the index <code>index-metadata-party-organizations-uuid</code> using a key constructed of key field(s) <code>.</code></p>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/parties/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/party/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/responsible-parties" class="toc3 name">responsible-parties</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/responsible-parties">(global definition)</a></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Responsible Party</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A reference to a set of persons and/or organizations that have responsibility for
                              performing the referenced role in the context of the containing object.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>A <code>responsible-party</code> requires one or more <code>party-uuid</code> references creating a strong relationship arc between the referenced <code>role-id</code> and the reference parties. This differs in semantics from <code>responsible-role</code> which doesn't require that a <code>party-uuid</code> is referenced.</p>
                                    <p>The scope of use of this object determines if the responsibility has been performed
                                       or will be performed in the future. The containing object will describe the intent.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="constraints" open="open">
                              <summary>Constraint (1)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">index has key</span>this value must correspond to a listing in the index <code>index-metadata-role-id</code> using a key constructed of key field(s) <code>@role-id</code></p>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (5)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/responsible-parties/role-id" class="toc4 name">role-id</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/@role-id">Switch to XML</a></div>
                                    <p class="formal-name">Responsible Role</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a <code>role</code> performed by a <code>party</code>.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/responsible-parties/party-uuids" class="toc4 name">party-uuids</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/party-uuid">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Party Universally Unique Identifier Reference</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Reference to a party by UUID.</p>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>this value must correspond to a listing in the index <code>index-metadata-party-uuid</code> using a key constructed of key field(s) <code>.</code></p>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/responsible-parties/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/responsible-party/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/responsible-parties/links" class="toc4 name">links</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/responsible-party/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/links/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/links/rel" class="toc5 name">rel</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/links/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/responsible-parties/links/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/responsible-parties/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/responsible-party/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/actions" class="toc3 name">actions</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/metadata/actions">(global definition)</a></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Action</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> An action applied by a role within a given party to the content.</p>
                           <details class="constraints" open="open">
                              <summary>Constraints (4)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">index has key</span>  for <code class="path">responsible-party</code>this value must correspond to a listing in the index <code>index-metadata-role-id</code> using a key constructed of key field(s) <code>@role-id</code></p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">index has key</span>  for <code class="path">responsible-party</code>this value must correspond to a listing in the index <code>index-metadata-party-uuid</code> using a key constructed of key field(s) <code>party-uuid</code></p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed value</span>  for <code class="path">./system/@value</code></p>
                                 <p>The value <b>may be locally defined</b>, or the following:</p>
                                 <ul>
                                    
                                    <li><strong>http://csrc.nist.gov/ns/oscal</strong>: This value identifies action types defined in the NIST OSCAL namespace.</li>
                                    </ul>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed values</span>  for <code class="path">./type[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@value</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>approval</strong>: An approval of a document instance's content.</li>
                                    
                                    <li><strong>request-changes</strong>: A request from the responisble party or parties to change the content.</li>
                                    </ul>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (8)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/uuid" class="toc4 name">uuid</h4>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/@uuid">Switch to XML</a></div>
                                    <p class="formal-name">Action Universally Unique Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A unique identifier that can be used to reference this defined action elsewhere in
                                       an OSCAL document. A UUID should be consistently used for a given location across
                                       revisions of the document.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/date" class="toc4 name">date</h4>
                                    <p class="type"><a href="/reference/datatypes/#datetime-with-timezone">dateTime-with-timezone</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/@date">Switch to XML</a></div>
                                    <p class="formal-name">Action Occurrence Date</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The date and time when the action occurred.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/type" class="toc4 name">type</h4>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/@type">Switch to XML</a></div>
                                    <p class="formal-name">Action Type</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The type of action documented by the assembly, such as an approval.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/system" class="toc4 name">system</h4>
                                    <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/@system">Switch to XML</a></div>
                                    <p class="formal-name">Action Type System</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Specifies the action type system used.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Provides a means to segment the value space for the <code>type</code>, so that different organizations and individuals can assert control over the allowed
                                                <code>action</code>'s <code>type</code>. This allows the semantics associated with a given <code>type</code> to be defined on an organization-by-organization basis.</p>
                                             <p>An organization MUST use a URI that they have control over. e.g., a domain registered
                                                to the organization in a URI, a registered uniform resource names (URN) namespace.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/action/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/links" class="toc4 name">links</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/action/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/links/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/links/rel" class="toc5 name">rel</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/links/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/links/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/responsible-parties" class="toc4 name">responsible-parties</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/action/responsible-parties">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Responsible Party</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a set of persons and/or organizations that have responsibility for
                                       performing the referenced role in the context of the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>A <code>responsible-party</code> requires one or more <code>party-uuid</code> references creating a strong relationship arc between the referenced <code>role-id</code> and the reference parties. This differs in semantics from <code>responsible-role</code> which doesn't require that a <code>party-uuid</code> is referenced.</p>
                                             <p>The scope of use of this object determines if the responsibility has been performed
                                                or will be performed in the future. The containing object will describe the intent.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>this value must correspond to a listing in the index <code>index-metadata-role-id</code> using a key constructed of key field(s) <code>@role-id</code></p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (5)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/responsible-parties/role-id" class="toc5 name">role-id</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/@role-id">Switch to XML</a></div>
                                             <p class="formal-name">Responsible Role</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to a <code>role</code> performed by a <code>party</code>.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/responsible-parties/party-uuids" class="toc5 name">party-uuids</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/party-uuid">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Party Universally Unique Identifier Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Reference to a party by UUID.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">index has key</span>this value must correspond to a listing in the index <code>index-metadata-party-uuid</code> using a key constructed of key field(s) <code>.</code></p>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/responsible-parties/props" class="toc5 name">props</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/responsible-party/props">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Property</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                                namespace qualified name/value pair.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                         OSCAL objects. A property can be included for any purpose useful to an application
                                                         or implementation. Typically, properties will be used to sort, filter, select, order,
                                                         and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                         an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                         lexical composition of properties may be constrained by external processes to ensure
                                                         consistency.</p>
                                                      <p>Property allows for associated remarks that describe why the specific property value
                                                         was applied to the containing object, or the significance of the value in the context
                                                         of the containing object.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="properties" open="open">
                                                <summary>Properties (7)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/name" class="toc6 name">name</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/@name">Switch to XML</a></div>
                                                      <p class="formal-name">Property Name</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                         characteristic, or quality of the property's containing object.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>must</b> be one of the following:</p>
                                                            <ul>
                                                               
                                                               
                                                               <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                                  An optional class can be used to define the specific marking system used for the associated
                                                                  value.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/uuid" class="toc6 name">uuid</h6>
                                                      <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/@uuid">Switch to XML</a></div>
                                                      <p class="formal-name">Property Universally Unique Identifier</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/ns" class="toc6 name">ns</h6>
                                                      <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/@ns">Switch to XML</a></div>
                                                      <p class="formal-name">Property Namespace</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                         associate distinct semantics with the same name.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                               <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/value" class="toc6 name">value</h6>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/@value">Switch to XML</a></div>
                                                      <p class="formal-name">Property Value</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/class" class="toc6 name">class</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/@class">Switch to XML</a></div>
                                                      <p class="formal-name">Property Class</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                                  properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                               <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                                  a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/group" class="toc6 name">group</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/@group">Switch to XML</a></div>
                                                      <p class="formal-name">Property Group</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                                  property to associate it with one or more other properties in a given context.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/props/remarks" class="toc6 name">remarks</h6>
                                                      <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/prop/remarks">Switch to XML</a></div>
                                                      <p class="formal-name">Remarks</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                                  by OSCAL.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/responsible-parties/links" class="toc5 name">links</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/link">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/responsible-party/links">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Link</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                                object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                         a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                                      <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraints (3)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                                </div>
                                             </details>
                                             <details class="properties" open="open">
                                                <summary>Properties (4)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/links/href" class="toc6 name">href</h6>
                                                      <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/link/@href">Switch to XML</a></div>
                                                      <p class="formal-name">Hypertext Reference</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value may be one of:</p>
                                                               <ol>
                                                                  
                                                                  <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                                  
                                                                  <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                                     document, or</li>
                                                                  
                                                                  <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                                     (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                                  </ol>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/links/rel" class="toc6 name">rel</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/link/@rel">Switch to XML</a></div>
                                                      <p class="formal-name">Link Relation Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                         can be an indicator of the link's purpose.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>may be locally defined</b>, or the following:</p>
                                                            <ul>
                                                               
                                                               <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                                  resource by UUID expressed as a bare URI fragment.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/links/media-type" class="toc6 name">media-type</h6>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/link/@media-type">Switch to XML</a></div>
                                                      <p class="formal-name">Media Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                               <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                               <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                                  specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                                  suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                               <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                                  <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                                  the initial content of the referenced resource.</p>
                                                            </div>
                                                            <div class="remarks">
                                                               <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                                  from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/metadata/actions/responsible-parties/links/text" class="toc6 name">text</h6>
                                                      <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/link/text">Switch to XML</a></div>
                                                      <p class="formal-name">Link Text</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                         a tool.</p>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/metadata/actions/responsible-parties/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/responsible-party/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/metadata/actions/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/action/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/metadata/remarks" class="toc3 name">remarks</h3>
                           <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/metadata/remarks">Switch to XML</a></div>
                           <p class="formal-name">Remarks</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                       by OSCAL.</p>
                                 </div>
                              </details>
                           </div>
                        </div>
                     </div>
                  </details>
               </div>
            </div>
            <div class="model-entry definition assembly">
               <div class="instance-header">
                  <h2 id="/mapping-collection/mappings" class="toc2 name">mappings</h2>
                  <p class="type">singleton-or-array<br /></p>
                  <p class="occurrence">[1]</p>
                  <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping">Switch to XML</a></div>
               </div>
               <div class="array-header">
                  <p class="array-member">(array member or singleton)</p>
                  <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping-collection/mappings">(global definition)</a></p>
                  <p class="occurrence">[1 to ∞]</p>
                  <p class="formal-name">Control Mapping</p>
               </div>
               <p class="description"><span class="usa-tag">Description</span> A mapping between two target resources.</p>
               <div class="body">
                  <p class="description"><span class="usa-tag">Description</span> A mapping between two target resources.</p>
                  <details class="properties" open="open">
                     <summary>Properties (4)</summary>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h4 id="/mapping-collection/mappings/mapping/uuid" class="toc4 name">uuid</h4>
                           <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/@uuid">Switch to XML</a></div>
                           <p class="formal-name">Mapping Universally Unique Identifier</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A <a href="/concepts/identifier-use/#machine-oriented">machine-oriented</a>, <a href="/concepts/identifier-use/#globally-unique">globally unique</a> identifier with <a href="/concepts/identifier-use/#cross-instance">cross-instance</a> scope that can be used to reference this mapping definition elsewhere in this or
                              other OSCAL instances. The locally defined <em>UUID</em> of the <code>mapping</code> can be used to reference the data item locally or globally (e.g., in an imported
                              OSCAL instance). This UUID should be assigned <a href="/concepts/identifier-use/#consistency">per-subject</a>, which means it should be consistently used to identify the same mapping across revisions
                              of the document.</p>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h4 id="/mapping-collection/mappings/mapping/source-resource" class="toc4 name">source-resource</h4>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping/source-resource">(global definition)</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource">Switch to XML</a></div>
                           <p class="formal-name">Mapped Resource Reference</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A reference to a resource that is either the source or target of a mapping.</p>
                           <details class="properties" open="open">
                              <summary>Properties (5)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/source-resource/type" class="toc5 name">type</h5>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/@type">Switch to XML</a></div>
                                    <p class="formal-name">Resource Type</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The semantic type of the resource.</p>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed value</span></p>
                                          <p>The value <b>must</b> be one of the following:</p>
                                          <ul>
                                             
                                             <li><strong>catalog</strong>: The mapped resource is a control catalog.</li>
                                             </ul>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/source-resource/href" class="toc5 name">href</h5>
                                    <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/@href">Switch to XML</a></div>
                                    <p class="formal-name">Catalog or Profile Reference</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to the base catalog or profile that this profile is tailoring.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This value may be one of:</p>
                                             <ol>
                                                
                                                <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                
                                                <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                   document, or</li>
                                                
                                                <li>a bare URI fragment (i.e., `#uuid`) pointing to a <code>back-matter</code> resource in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>).</li>
                                                </ol>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/source-resource/props" class="toc5 name">props</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-resource-reference/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/name" class="toc6 name">name</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/uuid" class="toc6 name">uuid</h6>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/ns" class="toc6 name">ns</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/value" class="toc6 name">value</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/class" class="toc6 name">class</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/group" class="toc6 name">group</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/props/remarks" class="toc6 name">remarks</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/source-resource/links" class="toc5 name">links</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-resource-reference/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/links/href" class="toc6 name">href</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/links/rel" class="toc6 name">rel</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/links/media-type" class="toc6 name">media-type</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/source-resource/links/text" class="toc6 name">text</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/source-resource/remarks" class="toc5 name">remarks</h5>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/source-resource/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h4 id="/mapping-collection/mappings/mapping/target-resource" class="toc4 name">target-resource</h4>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping/target-resource">(global definition)</a></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource">Switch to XML</a></div>
                           <p class="formal-name">Mapped Resource Reference</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A reference to a resource that is either the source or target of a mapping.</p>
                           <details class="properties" open="open">
                              <summary>Properties (5)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/target-resource/type" class="toc5 name">type</h5>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/@type">Switch to XML</a></div>
                                    <p class="formal-name">Resource Type</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The semantic type of the resource.</p>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed value</span></p>
                                          <p>The value <b>must</b> be one of the following:</p>
                                          <ul>
                                             
                                             <li><strong>catalog</strong>: The mapped resource is a control catalog.</li>
                                             </ul>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/target-resource/href" class="toc5 name">href</h5>
                                    <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/@href">Switch to XML</a></div>
                                    <p class="formal-name">Catalog or Profile Reference</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to the base catalog or profile that this profile is tailoring.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>This value may be one of:</p>
                                             <ol>
                                                
                                                <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                
                                                <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                   document, or</li>
                                                
                                                <li>a bare URI fragment (i.e., `#uuid`) pointing to a <code>back-matter</code> resource in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>).</li>
                                                </ol>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/target-resource/props" class="toc5 name">props</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-resource-reference/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/name" class="toc6 name">name</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/uuid" class="toc6 name">uuid</h6>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/ns" class="toc6 name">ns</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/value" class="toc6 name">value</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/class" class="toc6 name">class</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/group" class="toc6 name">group</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/props/remarks" class="toc6 name">remarks</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/target-resource/links" class="toc5 name">links</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-resource-reference/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/links/href" class="toc6 name">href</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/links/rel" class="toc6 name">rel</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/links/media-type" class="toc6 name">media-type</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/target-resource/links/text" class="toc6 name">text</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/target-resource/remarks" class="toc5 name">remarks</h5>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/target-resource/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h4 id="/mapping-collection/mappings/mapping/maps" class="toc4 name">maps</h4>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping/maps">(global definition)</a></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Mapping Entry</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A relationship-based mapping between a source and target set consisting of members
                              (i.e., controls, control statements) from the respective source and target.</p>
                           <details class="properties" open="open">
                              <summary>Properties (7)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/uuid" class="toc5 name">uuid</h5>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/@uuid">Switch to XML</a></div>
                                    <p class="formal-name">Mapping Entry Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The unique identifier for the mapping entry.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/props" class="toc5 name">props</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/map/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/name" class="toc6 name">name</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/uuid" class="toc6 name">uuid</h6>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/ns" class="toc6 name">ns</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/value" class="toc6 name">value</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/class" class="toc6 name">class</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/group" class="toc6 name">group</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/props/remarks" class="toc6 name">remarks</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/links" class="toc5 name">links</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/link">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/map/links">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                       object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                             <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraints (3)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                       </div>
                                       <div class="constraint">
                                          <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (4)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/links/href" class="toc6 name">href</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/link/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be one of:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         
                                                         <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                            (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/links/rel" class="toc6 name">rel</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/link/@rel">Switch to XML</a></div>
                                             <p class="formal-name">Link Relation Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                can be an indicator of the link's purpose.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                         resource by UUID expressed as a bare URI fragment.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/links/media-type" class="toc6 name">media-type</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/link/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                   <div class="remarks">
                                                      <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                         from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/links/text" class="toc6 name">text</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/link/text">Switch to XML</a></div>
                                             <p class="formal-name">Link Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                a tool.</p>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/relationship" class="toc5 name">relationship</h5>
                                    <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/relationship">Switch to XML</a></div>
                                    <p class="formal-name">Mapping Entry Relationship</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> The relationship type for the mapping entry, which describes the relationship between
                                       the effective requirements of the specified source and target sets.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>When establishing relationships, mapping SHOULD be done at the control statement level
                                                where possible. This approach allows for more use of 'equivalent-to', which represents
                                                a stronger relationship than the other relationship types.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="constraints" open="open">
                                       <summary>Constraint (1)</summary>
                                       <div class="constraint">
                                          <p><span class="usa-tag">allowed values</span>  for <code class="path">.[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]</code></p>
                                          <p>The value <b>must</b> be one of the following:</p>
                                          <ul>
                                             
                                             <li><strong>equivalent-to</strong>: The effective requirements of the source is equivalent in semantic meaning to the
                                                effective requirements of the target. The words may differ, but both mapped sets convey
                                                similar information with the same effective meaning. This relationship may be reversed,
                                                since `A equivalent-to B` also means that `B equivalent-to A`.</li>
                                             
                                             <li><strong>equal-to</strong>: The actual requirements of the source are the same as the actual requirements target.
                                                Differences in capitalization, spelling, and grammar can be ignored, if these differences
                                                do not change the meaning. This relationship may be reversed, since `A equal-to B`
                                                also means that `B equal-to A`.</li>
                                             
                                             <li><strong>subset-of</strong>: The effective requirements of the source is a semantic subset of the effective requirements
                                                of the target. This relationship may be reversed as a `superset-of`, since `A subset-of
                                                B` also means that `B superset-of A`.</li>
                                             
                                             <li><strong>superset-of</strong>: The effective requirements of the source is a semantic superset of the effective
                                                requirements of the target. This relationship may be reversed as a `subset-of`, since
                                                `A superset-of B` also means that `B subset-of A`.</li>
                                             
                                             <li><strong>intersects-with</strong>: The effective requirements of the source and target have some semantic equivalence,
                                                but not all effective requirements from each are contained within the other. This
                                                relationship may be reversed, since `A intersects-with B` also means that `B intersects-with
                                                A`. A lower granularity mapping, such as a statement level mapping using 'equivalent-to',
                                                'subset-of', and/or 'superset-of', may provide a more functional mapping that allows
                                                for more inference than using this relationship type.</li>
                                             </ul>
                                       </div>
                                    </details>
                                    <details class="properties" open="open">
                                       <summary>Properties (2)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/relationship/ns" class="toc6 name">ns</h6>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/relationship/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Relationship Value Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the relationship's value. This allows different organizations
                                                to associate distinct semantics for relationships with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/relationship/type" class="toc6 name">type</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/relationship/_VALUE">Switch to XML</a></div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/sources" class="toc5 name">sources</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/map/sources">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Mapping Entry Item (source or target)</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Identifies a specific edge within a source or target that is the subject of a mapping.</p>
                                    <details class="properties" open="open">
                                       <summary>Properties (5)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/sources/type" class="toc6 name">type</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/@type">Switch to XML</a></div>
                                             <p class="formal-name">Subject Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> The semantic type of the subject.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed values</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>control</strong>: A control as defined by OSCAL.</li>
                                                      
                                                      <li><strong>statement</strong>: A textual element of a control that defines part of the control's requirements.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/sources/id-ref" class="toc6 name">id-ref</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/@id-ref">Switch to XML</a></div>
                                             <p class="formal-name">Subject Identifier Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to an identified subject that is of the specified <code>type</code>.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/sources/props" class="toc6 name">props</h6>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-item/props">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Property</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                                namespace qualified name/value pair.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                         OSCAL objects. A property can be included for any purpose useful to an application
                                                         or implementation. Typically, properties will be used to sort, filter, select, order,
                                                         and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                         an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                         lexical composition of properties may be constrained by external processes to ensure
                                                         consistency.</p>
                                                      <p>Property allows for associated remarks that describe why the specific property value
                                                         was applied to the containing object, or the significance of the value in the context
                                                         of the containing object.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="properties" open="open">
                                                <summary>Properties (7)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/name" class="toc7 name">name</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/@name">Switch to XML</a></div>
                                                      <p class="formal-name">Property Name</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                         characteristic, or quality of the property's containing object.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>must</b> be one of the following:</p>
                                                            <ul>
                                                               
                                                               
                                                               <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                                  An optional class can be used to define the specific marking system used for the associated
                                                                  value.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/uuid" class="toc7 name">uuid</p>
                                                      <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/@uuid">Switch to XML</a></div>
                                                      <p class="formal-name">Property Universally Unique Identifier</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/ns" class="toc7 name">ns</p>
                                                      <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/@ns">Switch to XML</a></div>
                                                      <p class="formal-name">Property Namespace</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                         associate distinct semantics with the same name.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                               <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/value" class="toc7 name">value</p>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/@value">Switch to XML</a></div>
                                                      <p class="formal-name">Property Value</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/class" class="toc7 name">class</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/@class">Switch to XML</a></div>
                                                      <p class="formal-name">Property Class</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                                  properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                               <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                                  a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/group" class="toc7 name">group</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/@group">Switch to XML</a></div>
                                                      <p class="formal-name">Property Group</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                                  property to associate it with one or more other properties in a given context.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/props/remarks" class="toc7 name">remarks</p>
                                                      <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/prop/remarks">Switch to XML</a></div>
                                                      <p class="formal-name">Remarks</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                                  by OSCAL.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/sources/links" class="toc6 name">links</h6>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/link">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-item/links">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Link</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                                object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                         a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                                      <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraints (3)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                                </div>
                                             </details>
                                             <details class="properties" open="open">
                                                <summary>Properties (4)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/links/href" class="toc7 name">href</p>
                                                      <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/link/@href">Switch to XML</a></div>
                                                      <p class="formal-name">Hypertext Reference</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value may be one of:</p>
                                                               <ol>
                                                                  
                                                                  <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                                  
                                                                  <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                                     document, or</li>
                                                                  
                                                                  <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                                     (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                                  </ol>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/links/rel" class="toc7 name">rel</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/link/@rel">Switch to XML</a></div>
                                                      <p class="formal-name">Link Relation Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                         can be an indicator of the link's purpose.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>may be locally defined</b>, or the following:</p>
                                                            <ul>
                                                               
                                                               <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                                  resource by UUID expressed as a bare URI fragment.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/links/media-type" class="toc7 name">media-type</p>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/link/@media-type">Switch to XML</a></div>
                                                      <p class="formal-name">Media Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                               <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                               <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                                  specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                                  suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                               <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                                  <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                                  the initial content of the referenced resource.</p>
                                                            </div>
                                                            <div class="remarks">
                                                               <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                                  from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/sources/links/text" class="toc7 name">text</p>
                                                      <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/link/text">Switch to XML</a></div>
                                                      <p class="formal-name">Link Text</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                         a tool.</p>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/sources/remarks" class="toc6 name">remarks</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/source/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/targets" class="toc5 name">targets</h5>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/map/targets">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Mapping Entry Item (source or target)</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Identifies a specific edge within a source or target that is the subject of a mapping.</p>
                                    <details class="properties" open="open">
                                       <summary>Properties (5)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/targets/type" class="toc6 name">type</h6>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/@type">Switch to XML</a></div>
                                             <p class="formal-name">Subject Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> The semantic type of the subject.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed values</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>control</strong>: A control as defined by OSCAL.</li>
                                                      
                                                      <li><strong>statement</strong>: A textual element of a control that defines part of the control's requirements.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/targets/id-ref" class="toc6 name">id-ref</h6>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/@id-ref">Switch to XML</a></div>
                                             <p class="formal-name">Subject Identifier Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to an identified subject that is of the specified <code>type</code>.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/targets/props" class="toc6 name">props</h6>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-item/props">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Property</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                                namespace qualified name/value pair.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                         OSCAL objects. A property can be included for any purpose useful to an application
                                                         or implementation. Typically, properties will be used to sort, filter, select, order,
                                                         and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                         an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                         lexical composition of properties may be constrained by external processes to ensure
                                                         consistency.</p>
                                                      <p>Property allows for associated remarks that describe why the specific property value
                                                         was applied to the containing object, or the significance of the value in the context
                                                         of the containing object.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="properties" open="open">
                                                <summary>Properties (7)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/name" class="toc7 name">name</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/@name">Switch to XML</a></div>
                                                      <p class="formal-name">Property Name</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                         characteristic, or quality of the property's containing object.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>must</b> be one of the following:</p>
                                                            <ul>
                                                               
                                                               
                                                               <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                                  An optional class can be used to define the specific marking system used for the associated
                                                                  value.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/uuid" class="toc7 name">uuid</p>
                                                      <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/@uuid">Switch to XML</a></div>
                                                      <p class="formal-name">Property Universally Unique Identifier</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/ns" class="toc7 name">ns</p>
                                                      <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/@ns">Switch to XML</a></div>
                                                      <p class="formal-name">Property Namespace</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                         associate distinct semantics with the same name.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                               <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/value" class="toc7 name">value</p>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/@value">Switch to XML</a></div>
                                                      <p class="formal-name">Property Value</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/class" class="toc7 name">class</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/@class">Switch to XML</a></div>
                                                      <p class="formal-name">Property Class</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                                  properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                               <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                                  a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/group" class="toc7 name">group</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/@group">Switch to XML</a></div>
                                                      <p class="formal-name">Property Group</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                                  property to associate it with one or more other properties in a given context.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/props/remarks" class="toc7 name">remarks</p>
                                                      <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/prop/remarks">Switch to XML</a></div>
                                                      <p class="formal-name">Remarks</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                                  by OSCAL.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/targets/links" class="toc6 name">links</h6>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/link">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping-common/mapping-item/links">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Link</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                                object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                         a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                                      <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraints (3)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                                </div>
                                             </details>
                                             <details class="properties" open="open">
                                                <summary>Properties (4)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/links/href" class="toc7 name">href</p>
                                                      <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/link/@href">Switch to XML</a></div>
                                                      <p class="formal-name">Hypertext Reference</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value may be one of:</p>
                                                               <ol>
                                                                  
                                                                  <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                                  
                                                                  <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                                     document, or</li>
                                                                  
                                                                  <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                                     (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                                  </ol>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/links/rel" class="toc7 name">rel</p>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/link/@rel">Switch to XML</a></div>
                                                      <p class="formal-name">Link Relation Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                         can be an indicator of the link's purpose.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>may be locally defined</b>, or the following:</p>
                                                            <ul>
                                                               
                                                               <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                                  resource by UUID expressed as a bare URI fragment.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/links/media-type" class="toc7 name">media-type</p>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/link/@media-type">Switch to XML</a></div>
                                                      <p class="formal-name">Media Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                               <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                               <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                                  specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                                  suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                               <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                                  <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                                  the initial content of the referenced resource.</p>
                                                            </div>
                                                            <div class="remarks">
                                                               <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                                  from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <p id="/mapping-collection/mappings/mapping/maps/targets/links/text" class="toc7 name">text</p>
                                                      <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/link/text">Switch to XML</a></div>
                                                      <p class="formal-name">Link Text</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                         a tool.</p>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h6 id="/mapping-collection/mappings/mapping/maps/targets/remarks" class="toc6 name">remarks</h6>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/target/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h5 id="/mapping-collection/mappings/mapping/maps/remarks" class="toc5 name">remarks</h5>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/mapping/map/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                  </details>
               </div>
            </div>
            <div class="model-entry definition assembly">
               <div class="instance-header">
                  <h2 id="/mapping-collection/back-matter" class="toc2 name">back-matter</h2>
                  <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-mapping/mapping-collection/back-matter">(global definition)</a></p>
                  <p class="occurrence">[0 or 1]</p>
                  <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter">Switch to XML</a></div>
                  <p class="formal-name">Back matter</p>
               </div>
               <div class="body">
                  <p class="description"><span class="usa-tag">Description</span> A collection of resources that may be referenced from within the OSCAL document instance.</p>
                  <div class="remarks-group usa-prose">
                     <details open="open">
                        <summary class="subhead">Remarks</summary>
                        <div class="remarks">
                           <p>Provides a collection of identified <code>resource</code> objects that can be referenced by a <code>link</code> with a <code>rel</code> value of "reference" and an <code>href</code> value that is a fragment "#" followed by a reference to a reference's <code>uuid</code>. Other specialized link "rel" values also use this pattern when indicated in that
                              context of use.</p>
                        </div>
                        <div class="remarks">
                           <p>Back matter including references and resources.</p>
                        </div>
                     </details>
                  </div>
                  <details class="constraints" open="open">
                     <summary>Constraint (1)</summary>
                     <div class="constraint">
                        <p><span class="usa-tag">index</span>  for <code class="path">resource</code> an index <code>index-back-matter-resource</code> shall list values returned by targets <code>resource</code> using keys constructed of key field(s) <code>@uuid</code></p>
                     </div>
                  </details>
                  <details class="properties" open="open">
                     <summary>Property (1)</summary>
                     <div class="model-entry definition assembly">
                        <div class="instance-header">
                           <h3 id="/mapping-collection/back-matter/resources" class="toc3 name">resources</h3>
                           <p class="type">array<br /></p>
                           <p class="occurrence">[0 or 1]</p>
                           <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource">Switch to XML</a></div>
                        </div>
                        <div class="array-header">
                           <p class="array-member">(array member)</p>
                           <p class="type">object<br /></p>
                           <p class="occurrence">[1 to ∞]</p>
                           <p class="formal-name">Resource</p>
                        </div>
                        <div class="body">
                           <p class="description"><span class="usa-tag">Description</span> A resource associated with content in the containing document instance. A resource
                              may be directly included in the document using base64 encoding or may point to one
                              or more equivalent internet resources.</p>
                           <div class="remarks-group usa-prose">
                              <details open="open">
                                 <summary class="subhead">Remarks</summary>
                                 <div class="remarks">
                                    <p>A resource can be used in two ways. 1) it may point to an specific retrievable network
                                       resource using a <code>rlink</code>, or 2) it may be included as an attachment using a <code>base64</code>. A resource may contain multiple <code>rlink</code> and <code>base64</code> entries that represent alternative download locations (rlink) and attachments (base64)
                                       for the same resource.</p>
                                    <p>Both rlink and base64 allow for a <code>media-type</code> to be specified, which is used to distinguish between different representations of
                                       the same resource (e.g., Microsoft Word, PDF). When multiple <code>rlink</code> and <code>base64</code> items are included for a given resource, all items must contain equivalent information.
                                       This allows the document consumer to choose a preferred item to process based on a
                                       the selected item's <code>media-type</code>. This is extremely important when the items represent OSCAL content that is represented
                                       in alternate formats (i.e., XML, JSON, YAML), allowing the same OSCAL data to be processed
                                       from any of the available formats indicated by the items.</p>
                                    <p>When a resource includes a citation, then the <code>title</code> and <code>citation</code> properties must both be included.</p>
                                 </div>
                              </details>
                           </div>
                           <details class="constraints" open="open">
                              <summary>Constraints (6)</summary>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed values</span>  for <code class="path">prop/@name</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    <li><strong>type</strong>: Identifies the type of resource represented. The most specific appropriate type
                                       value SHOULD be used.</li>
                                    
                                    <li><strong>version</strong>: For resources representing a published document, this represents the version number
                                       of that document.</li>
                                    
                                    <li><strong>published</strong>: For resources representing a published document, this represents the publication
                                       date of that document.</li>
                                    </ul>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">matches</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='published']/@value</code>: the target value must match the lexical form of the 'dateTime-with-timezone' data
                                    type.</p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">allowed values</span>  for <code class="path">prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value</code></p>
                                 <p>The value <b>must</b> be one of the following:</p>
                                 <ul>
                                    
                                    
                                    <li><strong>logo</strong>: Indicates the resource is an organization's logo.</li>
                                    
                                    <li><strong>image</strong>: Indicates the resource represents an image.</li>
                                    
                                    <li><strong>screen-shot</strong>: Indicates the resource represents an image of screen content. </li>
                                    
                                    <li><strong>law</strong>: Indicates the resource represents an applicable law.</li>
                                    
                                    <li><strong>regulation</strong>: Indicates the resource represents an applicable regulation.</li>
                                    
                                    <li><strong>standard</strong>: Indicates the resource represents an applicable standard.</li>
                                    
                                    <li><strong>external-guidance</strong>: Indicates the resource represents applicable guidance.</li>
                                    
                                    <li><strong>acronyms</strong>: Indicates the resource provides a list of relevant acronyms.</li>
                                    
                                    <li><strong>citation</strong>: Indicates the resource cites relevant information.</li>
                                    
                                    
                                    <li><strong>policy</strong>: Indicates the resource is a policy.</li>
                                    
                                    <li><strong>procedure</strong>: Indicates the resource is a procedure.</li>
                                    
                                    <li><strong>system-guide</strong>: Indicates the resource is guidance document related to the subject system of an
                                       SSP.</li>
                                    
                                    <li><strong>users-guide</strong>: Indicates the resource is guidance document a user's guide or administrator's guide.</li>
                                    
                                    <li><strong>administrators-guide</strong>: Indicates the resource is guidance document a administrator's guide.</li>
                                    
                                    <li><strong>rules-of-behavior</strong>: Indicates the resource represents rules of behavior content.</li>
                                    
                                    <li><strong>plan</strong>: Indicates the resource represents a plan.</li>
                                    
                                    
                                    <li><strong>artifact</strong>: Indicates the resource represents an artifact, such as may be reviewed by an assessor.</li>
                                    
                                    <li><strong>evidence</strong>: Indicates the resource represents evidence, such as to support an assessment finding.</li>
                                    
                                    <li><strong>tool-output</strong>: Indicates the resource represents output from a tool.</li>
                                    
                                    <li><strong>raw-data</strong>: Indicates the resource represents machine data, which may require a tool or analysis
                                       for interpretation or presentation.</li>
                                    
                                    <li><strong>interview-notes</strong>: Indicates the resource represents notes from an interview, such as may be collected
                                       during an assessment.</li>
                                    
                                    <li><strong>questionnaire</strong>: Indicates the resource is a set of questions, possibly with responses.</li>
                                    
                                    <li><strong>report</strong>: Indicates the resource is a report.</li>
                                    
                                    <li><strong>agreement</strong>: Indicates the resource is a formal agreement between two or more parties.</li>
                                    </ul>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">has cardinality</span>  for <code class="path">rlink|base64</code> the cardinality of  <code>rlink|base64</code> is constrained: <b>1</b>; maximum <b>unbounded</b>.</p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">is unique</span>  for <code class="path">rlink</code>: any target value must be unique (i.e., occur only once)</p>
                              </div>
                              <div class="constraint">
                                 <p><span class="usa-tag">is unique</span>  for <code class="path">base64</code>: any target value must be unique (i.e., occur only once)</p>
                              </div>
                           </details>
                           <details class="properties" open="open">
                              <summary>Properties (9)</summary>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/uuid" class="toc4 name">uuid</h4>
                                    <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                    <p class="occurrence">[1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/@uuid">Switch to XML</a></div>
                                    <p class="formal-name">Resource Universally Unique Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A unique identifier for a resource.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/title" class="toc4 name">title</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/title">Switch to XML</a></div>
                                    <p class="formal-name">Resource Title</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An optional name given to the resource, which may be used by a tool for display and
                                       navigation.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/description" class="toc4 name">description</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/description">Switch to XML</a></div>
                                    <p class="formal-name">Resource Description</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An optional short summary of the resource used to indicate the purpose of the resource.</p>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/props" class="toc4 name">props</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/back-matter/resources/props">(global definition)</a></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Property</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                       namespace qualified name/value pair.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                OSCAL objects. A property can be included for any purpose useful to an application
                                                or implementation. Typically, properties will be used to sort, filter, select, order,
                                                and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                lexical composition of properties may be constrained by external processes to ensure
                                                consistency.</p>
                                             <p>Property allows for associated remarks that describe why the specific property value
                                                was applied to the containing object, or the significance of the value in the context
                                                of the containing object.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (7)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/name" class="toc5 name">name</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/@name">Switch to XML</a></div>
                                             <p class="formal-name">Property Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                characteristic, or quality of the property's containing object.</p>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>must</b> be one of the following:</p>
                                                   <ul>
                                                      
                                                      
                                                      <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                         An optional class can be used to define the specific marking system used for the associated
                                                         value.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/uuid" class="toc5 name">uuid</h5>
                                             <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/@uuid">Switch to XML</a></div>
                                             <p class="formal-name">Property Universally Unique Identifier</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/ns" class="toc5 name">ns</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/@ns">Switch to XML</a></div>
                                             <p class="formal-name">Property Namespace</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                associate distinct semantics with the same name.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                      <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/@value">Switch to XML</a></div>
                                             <p class="formal-name">Property Value</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/class" class="toc5 name">class</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/@class">Switch to XML</a></div>
                                             <p class="formal-name">Property Class</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                         properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                      <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                         a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/group" class="toc5 name">group</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/@group">Switch to XML</a></div>
                                             <p class="formal-name">Property Group</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                         property to associate it with one or more other properties in a given context.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/props/remarks" class="toc5 name">remarks</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/prop/remarks">Switch to XML</a></div>
                                             <p class="formal-name">Remarks</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                         by OSCAL.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/document-ids" class="toc4 name">document-ids</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/document-id">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                    <p class="occurrence">[0 to ∞]</p>
                                    <p class="formal-name">Document Identifier</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A document identifier qualified by an identifier <code>scheme</code>.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>A document identifier provides a <a href="/concepts/identifier-use/#globally-unique">globally unique</a> identifier with a <a href="/concepts/identifier-use/#cross-instance">cross-instance</a> scope that is used for a group of documents that are to be treated as different versions,
                                                representations or digital surrogates of the same document.</p>
                                             <p>A document identifier provides an additional data point for identifying a document
                                                that can be assigned by a publisher or organization for purposes in a wider system,
                                                such as a digital object identifier (DOI) or a local content management system identifier.</p>
                                             <p>Use of a document identifier allows for document creators to associate sets of documents
                                                that are related in some way by the same <code>document-id</code>.</p>
                                             <p>An OSCAL document always has an implicit document identifier provided by the document's
                                                UUID, defined by the <code>uuid</code> on the top-level object. Having a default UUID-based identifier ensures all documents
                                                can be minimally identified when other document identifiers are not provided.</p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (2)</summary>
                                       <div class="model-entry definition field">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/document-ids/scheme" class="toc5 name">scheme</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/document-id/@scheme">Switch to XML</a></div>
                                             <p class="formal-name">Document Identification Scheme</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Qualifies the kind of document identifier using a URI. If the scheme is not provided
                                                the value of the element will be interpreted as a string of characters.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraint (1)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">allowed value</span></p>
                                                   <p>The value <b>may be locally defined</b>, or the following:</p>
                                                   <ul>
                                                      
                                                      <li><strong>http://www.doi.org/</strong>: A Digital Object Identifier (DOI); use is preferred, since this allows for retrieval
                                                         of a full bibliographic record.</li>
                                                      </ul>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition field">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/document-ids/identifier" class="toc5 name">identifier</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/document-id/_VALUE">Switch to XML</a></div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/citation" class="toc4 name">citation</h4>
                                    <p class="type">object<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation">Switch to XML</a></div>
                                    <p class="formal-name">Citation</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> An optional citation consisting of end note text using structured markup.</p>
                                    <details class="properties" open="open">
                                       <summary>Properties (3)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/citation/text" class="toc5 name">text</h5>
                                             <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/text">Switch to XML</a></div>
                                             <p class="formal-name">Citation Text</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A line of citation text.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/citation/props" class="toc5 name">props</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/back-matter/resources/citation/props">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Property</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> An attribute, characteristic, or quality of the containing object expressed as a
                                                namespace qualified name/value pair.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>Properties permit the deployment and management of arbitrary controlled values, within
                                                         OSCAL objects. A property can be included for any purpose useful to an application
                                                         or implementation. Typically, properties will be used to sort, filter, select, order,
                                                         and arrange OSCAL content objects, to relate OSCAL objects to one another, or to associate
                                                         an OSCAL object to class hierarchies, taxonomies, or external authorities. Thus, the
                                                         lexical composition of properties may be constrained by external processes to ensure
                                                         consistency.</p>
                                                      <p>Property allows for associated remarks that describe why the specific property value
                                                         was applied to the containing object, or the significance of the value in the context
                                                         of the containing object.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="properties" open="open">
                                                <summary>Properties (7)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/name" class="toc6 name">name</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/@name">Switch to XML</a></div>
                                                      <p class="formal-name">Property Name</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label, within a namespace, that uniquely identifies a specific attribute,
                                                         characteristic, or quality of the property's containing object.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>must</b> be one of the following:</p>
                                                            <ul>
                                                               
                                                               
                                                               <li><strong>marking</strong>: A label or descriptor that is tied to a sensitivity or classification marking system.
                                                                  An optional class can be used to define the specific marking system used for the associated
                                                                  value.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/uuid" class="toc6 name">uuid</h6>
                                                      <p class="type"><a href="/reference/datatypes/#uuid">uuid</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/@uuid">Switch to XML</a></div>
                                                      <p class="formal-name">Property Universally Unique Identifier</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A unique identifier for a property.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/ns" class="toc6 name">ns</h6>
                                                      <p class="type"><a href="/reference/datatypes/#uri">uri</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/@ns">Switch to XML</a></div>
                                                      <p class="formal-name">Property Namespace</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A namespace qualifying the property's name. This allows different organizations to
                                                         associate distinct semantics with the same name.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value must be an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that serves as a <a href="/OSCAL/concepts/uri-use/#use-as-a-naming-system-identifier">naming system identifier</a>.</p>
                                                               <p>When a <code>ns</code> is not provided, its value should be assumed to be <code>http://csrc.nist.gov/ns/oscal</code> and the name should be a name defined by the associated OSCAL model.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/value" class="toc6 name">value</h6>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/@value">Switch to XML</a></div>
                                                      <p class="formal-name">Property Value</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Indicates the value of the attribute, characteristic, or quality.</p>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/class" class="toc6 name">class</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/@class">Switch to XML</a></div>
                                                      <p class="formal-name">Property Class</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label that provides a sub-type or characterization of the property's <code>name</code>.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This can be used to further distinguish or discriminate between the semantics of multiple
                                                                  properties of the same object with the same <code>name</code> and <code>ns</code>, or to group properties into categories.</p>
                                                               <p>A <code>class</code> can be used in validation rules to express extra constraints over named items of
                                                                  a specific <code>class</code> value. It is available for grouping, but unlike <code>group</code> is not expected specifically to designate any group membership as such.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/group" class="toc6 name">group</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/@group">Switch to XML</a></div>
                                                      <p class="formal-name">Property Group</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> An identifier for relating distinct sets of properties.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>Different sets of properties may relate to separate contexts. Declare a group on a
                                                                  property to associate it with one or more other properties in a given context.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/props/remarks" class="toc6 name">remarks</h6>
                                                      <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/prop/remarks">Switch to XML</a></div>
                                                      <p class="formal-name">Remarks</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                                  by OSCAL.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/citation/links" class="toc5 name">links</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/link">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type">object<br /> <a class="definition-link" href="../json-definitions/#/assembly/oscal-metadata/back-matter/resources/citation/links">(global definition)</a></p>
                                             <p class="occurrence">[1 to ∞]</p>
                                             <p class="formal-name">Link</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A reference to a local or remote resource, that has a specific relation to the containing
                                                object.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>To provide a cryptographic hash for a remote target resource, a local reference to
                                                         a back matter <code>resource</code> is needed. The resource allows one or more hash values to be provided using the <code>rlink/hash</code> object.</p>
                                                      <p>The OSCAL <code>link</code> is a roughly based on the HTML <a href="https://www.w3.org/TR/html401/struct/links.html#edef-LINK">link element</a>. </p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraints (3)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]/@href</code>: the target value must match the lexical form of the 'uri-reference' data type.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">index has key</span>  for <code class="path">.[@rel=('reference') and starts-with(@href,'#')]</code>this value must correspond to a listing in the index <code>index-back-matter-resource</code> using a key constructed of key field(s) <code>@href</code></p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@rel=('reference') and not(starts-with(@href,'#'))]/@href</code>: the target value must match the lexical form of the 'uri' data type.</p>
                                                </div>
                                             </details>
                                             <details class="properties" open="open">
                                                <summary>Properties (4)</summary>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/links/href" class="toc6 name">href</h6>
                                                      <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/link/@href">Switch to XML</a></div>
                                                      <p class="formal-name">Hypertext Reference</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A resolvable URL reference to a resource.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>This value may be one of:</p>
                                                               <ol>
                                                                  
                                                                  <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                                  
                                                                  <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                                     document, or</li>
                                                                  
                                                                  <li>a bare URI fragment (i.e., `#uuid`) pointing to an OSCAL object by the objects identifier
                                                                     (e.g., id, uuid) in this or an imported document (see <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#linking-to-another-oscal-object">linking to another OSCAL object</a>). The specific object type will differ based on the link relationship type.</li>
                                                                  </ol>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/links/rel" class="toc6 name">rel</h6>
                                                      <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/link/@rel">Switch to XML</a></div>
                                                      <p class="formal-name">Link Relation Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> Describes the type of relationship provided by the link's hypertext reference. This
                                                         can be an indicator of the link's purpose.</p>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed value</span></p>
                                                            <p>The value <b>may be locally defined</b>, or the following:</p>
                                                            <ul>
                                                               
                                                               <li><strong>reference</strong>: A generalized reference to a network resource (relative or absolute) or to a back-matter
                                                                  resource by UUID expressed as a bare URI fragment.</li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/links/media-type" class="toc6 name">media-type</h6>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/link/@media-type">Switch to XML</a></div>
                                                      <p class="formal-name">Media Type</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                               <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                               <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                                  specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                                  suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                               <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                                  <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                                  the initial content of the referenced resource.</p>
                                                            </div>
                                                            <div class="remarks">
                                                               <p>The <code>media-type</code> provides a hint about the content model of the referenced resource. A valid entry
                                                                  from the <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">IANA Media Types registry</a> SHOULD be used.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition assembly">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/citation/links/text" class="toc6 name">text</h6>
                                                      <p class="type"><a href="/reference/datatypes/#markup-line">markup-line</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/citation/link/text">Switch to XML</a></div>
                                                      <p class="formal-name">Link Text</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> A textual label to associate with the link, which may be used for presentation in
                                                         a tool.</p>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/rlinks" class="toc4 name">rlinks</h4>
                                    <p class="type">array<br /></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/rlink">Switch to XML</a></div>
                                 </div>
                                 <div class="array-header">
                                    <p class="array-member">(array member)</p>
                                    <p class="type">object<br /></p>
                                    <p class="occurrence">[1 to ∞]</p>
                                    <p class="formal-name">Resource link</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A URL-based pointer to an external resource with an optional hash for verification
                                       and change detection.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>Multiple <code>rlink</code> objects can be included for a resource. In such a case, all provided <code>rlink</code> items are intended to be equivalent in content, but may differ in structure or format.</p>
                                             <p>A <code>media-type</code> is used to identify the format of a given rlink, and can be used to differentiate
                                                items in a collection of rlinks. The <code>media-type</code> provides a hint to the OSCAL document consumer about the structure of the resource
                                                referenced by the <code>rlink</code>. </p>
                                          </div>
                                       </details>
                                    </div>
                                    <details class="properties" open="open">
                                       <summary>Properties (3)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/rlinks/href" class="toc5 name">href</h5>
                                             <p class="type"><a href="/reference/datatypes/#uri-reference">uri-reference</a></p>
                                             <p class="occurrence">[1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/rlink/@href">Switch to XML</a></div>
                                             <p class="formal-name">Hypertext Reference</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A resolvable URL pointing to the referenced resource.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>This value may be either:</p>
                                                      <ol>
                                                         
                                                         <li>an <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#absolute-uri">absolute URI</a> that points to a network resolvable resource,</li>
                                                         
                                                         <li>a <a href="https://pages.nist.gov/OSCAL/concepts/uri-use/#relative-reference">relative reference</a> pointing to a network resolvable resource whose base URI is the URI of the containing
                                                            document, or</li>
                                                         </ol>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/rlinks/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/rlink/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/rlinks/hashes" class="toc5 name">hashes</h5>
                                             <p class="type">array<br /></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/rlink/hash">Switch to XML</a></div>
                                          </div>
                                          <div class="array-header">
                                             <p class="array-member">(array member)</p>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 to ∞]</p>
                                             <p class="formal-name">Hash</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A representation of a cryptographic digest generated over a resource using a specified
                                                hash algorithm.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p>The <code>hash</code> value can be used to confirm that the resource referenced by the <code>href</code> is the same resources that was hashed by retrieving the resource, calculating a hash,
                                                         and comparing the result to this value.</p>
                                                   </div>
                                                </details>
                                             </div>
                                             <details class="constraints" open="open">
                                                <summary>Constraints (4)</summary>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@algorithm=('SHA-224','SHA3-224')</code>: a target (value) must match the regular expression '^[0-9a-fA-F]{28}$'.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@algorithm=('SHA-256','SHA3-256')</code>: a target (value) must match the regular expression '^[0-9a-fA-F]{32}$'.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@algorithm=('SHA-384','SHA3-384')</code>: a target (value) must match the regular expression '^[0-9a-fA-F]{48}$'.</p>
                                                </div>
                                                <div class="constraint">
                                                   <p><span class="usa-tag">matches</span>  for <code class="path">.[@algorithm=('SHA-512','SHA3-512')</code>: a target (value) must match the regular expression '^[0-9a-fA-F]{64}$'.</p>
                                                </div>
                                             </details>
                                             <details class="properties" open="open">
                                                <summary>Properties (2)</summary>
                                                <div class="model-entry definition field">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/rlinks/hashes/algorithm" class="toc6 name">algorithm</h6>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/rlink/hash/@algorithm">Switch to XML</a></div>
                                                      <p class="formal-name">Hash algorithm</p>
                                                   </div>
                                                   <div class="body">
                                                      <p class="description"><span class="usa-tag">Description</span> The digest method by which a hash is derived.</p>
                                                      <div class="remarks-group usa-prose">
                                                         <details open="open">
                                                            <summary class="subhead">Remarks</summary>
                                                            <div class="remarks">
                                                               <p>Any other value used MUST be a value defined in the W3C <a href="https://www.w3.org/TR/xmlsec-algorithms/#digest-method-uris">XML Security Algorithm Cross-Reference</a> Digest Methods (W3C, April 2013) or <a href="https://tools.ietf.org/html/rfc6931#section-2.1.5">RFC 6931 Section 2.1.5</a> New SHA Functions.</p>
                                                            </div>
                                                         </details>
                                                      </div>
                                                      <details class="constraints" open="open">
                                                         <summary>Constraint (1)</summary>
                                                         <div class="constraint">
                                                            <p><span class="usa-tag">allowed values</span></p>
                                                            <p>The value <b>may be locally defined</b>, or one of the following:</p>
                                                            <ul>
                                                               
                                                               <li><strong>SHA-224</strong>: The SHA-224 algorithm as defined by NIST FIPS 180-4.
                                                                  </li>
                                                               
                                                               <li><strong>SHA-256</strong>: The SHA-256 algorithm as defined by NIST FIPS 180-4.
                                                                  </li>
                                                               
                                                               <li><strong>SHA-384</strong>: The SHA-384 algorithm as defined by NIST FIPS 180-4.
                                                                  </li>
                                                               
                                                               <li><strong>SHA-512</strong>: The SHA-512 algorithm as defined by NIST FIPS 180-4.
                                                                  </li>
                                                               
                                                               <li><strong>SHA3-224</strong>: The SHA3-224 algorithm as defined by NIST FIPS 202.
                                                                  </li>
                                                               
                                                               <li><strong>SHA3-256</strong>: The SHA3-256 algorithm as defined by NIST FIPS 202.
                                                                  </li>
                                                               
                                                               <li><strong>SHA3-384</strong>: The SHA3-384 algorithm as defined by NIST FIPS 202.
                                                                  </li>
                                                               
                                                               <li><strong>SHA3-512</strong>: The SHA3-512 algorithm as defined by NIST FIPS 202.
                                                                  </li>
                                                               </ul>
                                                         </div>
                                                      </details>
                                                   </div>
                                                </div>
                                                <div class="model-entry definition field">
                                                   <div class="instance-header">
                                                      <h6 id="/mapping-collection/back-matter/resources/rlinks/hashes/value" class="toc6 name">value</h6>
                                                      <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                                      <p class="occurrence">[0 or 1]</p>
                                                      <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/rlink/hash/_VALUE">Switch to XML</a></div>
                                                   </div>
                                                </div>
                                             </details>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/base64" class="toc4 name">base64</h4>
                                    <p class="type"><a href="/reference/datatypes/#base64binary">base64Binary</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/base64">Switch to XML</a></div>
                                    <p class="formal-name">Base64</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> A resource encoded using the Base64 alphabet defined by <a href="https://www.rfc-editor.org/rfc/rfc2045.html">RFC 2045</a>.</p>
                                    <details class="properties" open="open">
                                       <summary>Properties (3)</summary>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/base64/filename" class="toc5 name">filename</h5>
                                             <p class="type"><a href="/reference/datatypes/#token">token</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/base64/@filename">Switch to XML</a></div>
                                             <p class="formal-name">File Name</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> Name of the file before it was encoded as Base64 to be embedded in a <code>resource</code>. This is the name that will be assigned to the file when the file is decoded.</p>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/base64/media-type" class="toc5 name">media-type</h5>
                                             <p class="type"><a href="/reference/datatypes/#string">string</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/base64/@media-type">Switch to XML</a></div>
                                             <p class="formal-name">Media Type</p>
                                          </div>
                                          <div class="body">
                                             <p class="description"><span class="usa-tag">Description</span> A label that indicates the nature of a resource, as a data serialization or format.</p>
                                             <div class="remarks-group usa-prose">
                                                <details open="open">
                                                   <summary class="subhead">Remarks</summary>
                                                   <div class="remarks">
                                                      <p> The Internet Assigned Numbers Authority (IANA) <a href="https://www.iana.org/assignments/media-types/media-types.xhtml">Media Types Registry</a> defines a standardized set of media types, which may be used here.</p>
                                                      <p>The <code>application/oscal+xml</code>, <code>application/oscal+json</code> or <code>application/oscal+yaml</code> media types SHOULD be used when referencing OSCAL XML, JSON, or YAML resources respectively.</p>
                                                      <p>**Note: There is no official media type for YAML at this time.** OSCAL documents should
                                                         specify <code>application/yaml</code> for general YAML content, or <code>application/oscal+yaml</code> for YAML-based OSCAL content. This approach aligns with use of a structured name
                                                         suffix, per <a href="https://www.rfc-editor.org/rfc/rfc6838.html#section-4.2.8">RFC 6838 Section 4.2.8</a>.</p>
                                                      <p>Some earlier OSCAL content incorporated the model into the media type. For example:
                                                         <code>application/oscal.catalog+xml</code>. This practice SHOULD be avoided, since the OSCAL model can be detected by parsing
                                                         the initial content of the referenced resource.</p>
                                                   </div>
                                                </details>
                                             </div>
                                          </div>
                                       </div>
                                       <div class="model-entry definition assembly">
                                          <div class="instance-header">
                                             <h5 id="/mapping-collection/back-matter/resources/base64/value" class="toc5 name">value</h5>
                                             <p class="type"><a href="/reference/datatypes/#base64binary">base64Binary</a></p>
                                             <p class="occurrence">[0 or 1]</p>
                                             <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/base64/_VALUE">Switch to XML</a></div>
                                          </div>
                                       </div>
                                    </details>
                                 </div>
                              </div>
                              <div class="model-entry definition assembly">
                                 <div class="instance-header">
                                    <h4 id="/mapping-collection/back-matter/resources/remarks" class="toc4 name">remarks</h4>
                                    <p class="type"><a href="/reference/datatypes/#markup-multiline">markup-multiline</a></p>
                                    <p class="occurrence">[0 or 1]</p>
                                    <div class="crosslink"><a class="usa-button" href="../xml-reference/#/mapping-collection/back-matter/resource/remarks">Switch to XML</a></div>
                                    <p class="formal-name">Remarks</p>
                                 </div>
                                 <div class="body">
                                    <p class="description"><span class="usa-tag">Description</span> Additional commentary about the containing object.</p>
                                    <div class="remarks-group usa-prose">
                                       <details open="open">
                                          <summary class="subhead">Remarks</summary>
                                          <div class="remarks">
                                             <p>The <code>remarks</code> field SHOULD not be used to store arbitrary data. Instead, a <code>prop</code> or <code>link</code> should be used to annotate or reference any additional data not formally supported
                                                by OSCAL.</p>
                                          </div>
                                       </details>
                                    </div>
                                 </div>
                              </div>
                           </details>
                        </div>
                     </div>
                  </details>
               </div>
            </div>
         </details>
      </div>
   </div>
</div>{{< /rawhtml >}}
