# KEP Format to Propose and Document Enhancements to Kubeflow

## Summary

A standardized development process for Kubeflow is recommended, when the scope is sufficiently large, in order to:

- provide a common structure for proposing changes to Kubeflow
- ensure that the motivation for a change is clear
- allow for the enumeration of stability milestones and stability graduation
  criteria
- persist project information in a Version Control System (VCS) for future
  contributors
- support the creation of _high-value, user-facing_ information such as:
  - an overall project development roadmap
  - motivation for impactful user-facing changes
- reserve GitHub issues for tracking work in flight, instead of creating "umbrella"
  issues
- ensure community participants can successfully drive changes to
  completion across one or more releases while stakeholders are adequately
  represented throughout the process

This process is supported by a unit of work of the Kubeflow Enhancement Proposal format, or KEP for short.
A KEP attempts to combine aspects of

- a feature, and effort-tracking document
- a product requirements document
- a design document

into one file.

We are proposing usage of KEPs in Kubeflow to be better aligned with the wider Kubernetes community.

This proposal takes heavy inspiration from the [Kubernetes KEP Proposal](https://github.com/kubernetes/enhancements/blob/master/keps/sig-architecture/0000-kep-process/README.md)

## Motivation

Documenting proposals and enhancements are critical in managing the complexity and longevity of software projects.

Some examples include:

1. Capturing the "why" behind critical architectural choices, not just the what.
   1. This helps current and future team members understand the reasoning behind decisions, particularly when the rationale is no longer obvious.
2. Improve Communication and Collaboration.
3. Serve as a single source of truth for architectural decisions.
4. By documenting options and their trade-offs, KEPs encourage structured decision-making and transparency.
5. Enable Traceability
6. Create a decision history that allows new (and old) contributors to trace architectural choices back to their original context, assumptions, and goals

### Goals

- Capture the Why Behind Decisions
- Foster Clear Communication
- Enable Decision Traceability
- Encourage Thoughtful, Deliberate Decisions
- Preserve Institutional Knowledge

### Non-Goals

- Not a substitute for technical or user documentation
- Not a substitute or replacement for meaningful commit messages

## Proposal

A KEP is broken into sections which can be merged into source control
incrementally in order to support an iterative development process. The KEP process
is intended to create high-quality, uniform design and implementation documents
for maintainers to deliberate. Contributors proposing new KEPs should create a copy
of the [template directory](./NNNN-template) and proceed as per the instructions in the template.

## Reference-Level Explanation

### What Type of Work Should Be Tracked by a KEP

Roughly any user or operator facing enhancement should follow the KEP process.
If an enhancement would be described in either written or verbal communication
to anyone besides the KEP author or developer, then consider creating a KEP.

Similarly, any technical effort (refactoring, major architectural change) that
will significantly impact a large section of the development community should also be
communicated widely. The KEP process is suited for this even if it will have
zero impact on the typical user or operator.

### KEP Workflow

A KEP has the following states:

- `provisional`: The KEP has been proposed and is actively being defined.
  This is the starting state while the KEP is being fleshed out and actively defined and discussed.
  The owning SIG has accepted that this work must be done.
- `implementable`: The approvers have approved this KEP for implementation.
- `implemented`: The KEP has been implemented and is no longer actively changed.
- `deferred`: The KEP is proposed but not actively being worked on.
- `rejected`: The approvers and authors have decided that this KEP is not moving forward.
  The KEP is kept around as a historical document.
- `withdrawn`: The authors have withdrawn the KEP.
- `replaced`: The KEP has been replaced by a new KEP.
  The `superseded-by` metadata value should point to the new KEP.

Some authors may prefer to prepare a Google Doc (or similar) before creating a KEP on GitHub.
While not a required part of the process, it may be useful to quickly gather initial community feedback.

We strongly advise KEP authors to present their KEPs in relevant Kubeflow Working Group meetings or the
wider community meeting as relevant. This will help gather community feedback and bring visibility to
upcoming changes

### Git and GitHub Implementation

KEPs are checked into the component repo under the `proposals` directory. Note that there isn't yet a standard for where this directory is located.
Some components locate their KEPS at `./docs/proposals`, whereas other components have their KEPS located at `./proposals`

KEPs affecting multiple Kubeflow projects that do not fit into existing cross-component projects such as `kubeflow/manifests` should be created under `kubeflow/community`

- New KEPs can be checked in with a file name in the form of `XYZ-my-title.md`, where XYZ is a KEP number.
- As significant work is done on the KEP, the authors can assign a KEP number.
  - If there isn't already a tracking issue for the KEP in the approriate repository, create it. This issue number should then be used as the KEP number
- No other changes should be put in that PR so that it can be approved quickly and minimize merge conflicts.
- The KEP number can also be done as part of the initial submission if the PR is likely to be uncontested and merged quickly.

### Prior Art

Our usage of the KEP process (and most of this file) is almost entirely based on the
[Kubernetes KEP Process](https://github.com/kubernetes/enhancements/blob/master/keps/sig-architecture/0000-kep-process/README.md)
