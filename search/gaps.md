# HCI / AR/VR / Visual Perception — Evidence Gaps and Closing Plans

**Student:** Zitiantao Lin  
**Review date:** 2026-10-29  
**Status:** Final for assignment submission. The plans below are future work; no deliverable is claimed as complete.

## Target and scope

Target: HCI / AR/VR research engineering focused on visual perception and interaction (see `profile.yml`). I already build gaze/MR systems, run user studies, evaluate vision results, and test software. Each row names an evidence package I still need to make inspectable for this target, not a skill I have never used.

My priority gap is **G3: XR testing and reproducible release**, rewritten in my own words. One Apple-native row was deleted, and an earlier G2 that underestimated my evaluation experience was corrected (both explained below).

## Demand sources

| ID | Source | Relevant demand | How it is used |
| --- | --- | --- | --- |
| **J1** | [FieldAI — 3D/AR/VR Software Engineer](https://jobs.lever.co/field-ai/e22d37a0-6247-4e20-8c63-cb2d84056b85) | Interaction prototypes evaluated and iterated through user studies; end-to-end debugging; testing, monitoring, deployment, and maintainable applications. | Primary posting. Boston, on-site, full time; accepts bachelor's/master's. Not labeled new grad. |
| **J2** | [Figure — Helix AI Engineer, XR](https://job-boards.greenhouse.io/figureai/jobs/4699095006) | XR interfaces, reliable data synchronization, low-latency transmission, headset/custom-hardware integration. | Technical reference for G2. San Jose; requires deep XR experience and strong C++. |
| **J3** | [Axon — Sr. Software Engineer, VR Internal Tools](https://job-boards.greenhouse.io/axon/jobs/6308836003) | Build/test/deployment automation, testing infrastructure, diagnostics, documentation. | Supplementary reference for G3 only. Requires 5+ years; not an eligibility match. |
| **O1** | [O\*NET 15-1252.00 Software Developers](https://www.onetonline.org/link/details/15-1252.00) (updated 2026) | Core tasks: "Develop or direct software system testing or validation procedures, programming, or documentation"; "Modify existing software to … upgrade interfaces and improve performance"; "Determine system performance standards". Supplemental: "Coordinate installation of software system". | Occupation-level baseline that does not depend on any single posting staying open. Used for G1 (interface upgrade), G2 (performance standards), and G3 (testing/validation, installation). It is generic software work, not XR-specific; the postings supply the XR context. |

Postings checked 2026-10-29. Sponsorship status and July 2027 availability are not established by any posting.

## Gap table

| Gap | Evidence the target demands it | What I have | Plan to close it |
| --- | --- | --- | --- |
| **G1 — Document an interaction iteration.** A reviewable chain from a user finding to an interface change and a follow-up evaluation. | **J1:** user-study-based prototyping, evaluation, and iteration. **O1:** modify existing software to upgrade interfaces. Comparing two input methods alone does not show that a finding caused a design revision. | GazeCastGrasp gaze-versus-keyboard study and gaze/MR implementation (`proj-03`). Study ability is established; a documented iteration case is not. | Recover existing observations and interface versions first. If no complete chain exists, take one observed interaction problem, record its baseline, implement one justified revision, and evaluate it under stated conditions. **Deliverable:** case study with finding, rationale, before/after artifacts, version, method, and results. **Close when:** a reviewer can trace the finding to the change and recompute the outcome. Null or adverse results are still reported; the original study is not relabeled as the follow-up. |
| **G2 — Produce reproducible runtime/synchronization evidence.** Timing measurements with explicit boundaries. | **J2:** reliable synchronization and low-latency transmission. **J1:** debugging and optimization across headsets, networks, and compute. **O1:** determine system performance standards. These are runtime requirements, separate from prediction accuracy. | Gaze/vision systems with accuracy and failure evaluation. No published runtime measurement for a defined path. | Instrument one workstation-side path in the same prototype: gaze-message reception to submission of the matching target-feedback message. Record boundaries, monotonic-clock method, hardware/software versions, workload, and sample count; compare baseline with one controlled processing-load condition; check message age or sequence alignment where data allow. **Deliverable:** measurement/analysis code, non-sensitive raw logs, latency distributions, stale-message analysis. **Close when:** a reviewer can rerun the measurement and reproduce the analysis. Scope: not full eye-to-display latency; cross-device timestamps are not subtracted without a supported clock method. |
| **G3 — Demonstrate XR testing and release capability.** *(Rewritten in my own words; Chinese original below.)* | FieldAI's 3D/AR/VR Software Engineer role (J1) requires delivering reliable, maintainable interaction applications through repeatable testing and deployment; this is my main reason for choosing this gap. Axon's VR Internal Tools role (J3) also values test execution, build/deployment workflows, and documentation, so this capability is worth building early. | In GazeCastGrasp, I built an MR prototype connecting gaze interaction, visual perception, and a Franka robotic arm, and completed a gaze-versus-keyboard comparison study. At Next Play, I develop and test web application features. These experiences show that I can implement interactive systems, run evaluations, and do routine software testing. However, I do not yet have an XR-specific test package that others can install and reproduce, and I need to fill this gap. | Run tests on a single prototype covering target selection, cancellation/reset, input expiration, and reconnection after disconnection. Clearly document the expected results, actual results, and execution steps. Provide the test code, test procedures, test outcomes, an installable version, and instructions for running the tests, so that others can install the build and replicate the checks. Label which tests are automated and which are manual. **Close when:** others can install the build and repeat the checks. |

## Personal modification 1 — Deleted the Apple-native row

The agent proposed an Apple / Swift / SwiftUI / ARKit gap before it knew my platform scope. I do not target Apple-native roles (now recorded as an exclusion in `profile.yml`); my XR work uses Unity/OpenXR. The row also had no posting behind it: its demand signal was the agent's generalization about XR roles, not a requirement from any posting I target. That made it an invented demand signal as well as an out-of-scope one. Deleting it does not mean I have Apple-native skills.

## Personal modification 2 — Rewrote G3 in my own words

I chose testing and reproducible release because an interaction prototype should be checkable through repeatable behavior tests and installation instructions, not only through a study or a demo. The G3 row above is my wording.

### My Chinese original

**Gap / Plan / Close when:**

> **G3：通过展示 XR 测试与发布能力**对同一个原型检查目标选择、取消／重置、输入过期、断线恢复等测试。写清预期结果、实际结果和运行步骤。**测试代码提供测试步骤、测试结果、可安装版本和运行说明**。别人可以安装并重复检查。分别自动测试与人工测试。

**Evidence the target demands it:**

> FieldAI 的 3D/AR/VR 软件工程师岗位要求通过可重复的测试和部署，交付可靠、可维护的交互应用，这是我选这个缺口的主要依据。Axon 的 VR 内部工具岗位也重视测试执行、构建部署流程和文档，所以这类能力值得我提前补齐。

**What I have:**

> 我在 GazeCastGrasp 中搭建了连接眼动交互、视觉感知和 Franka 机械臂的 MR 原型，并完成了眼动与键盘控制的对比实验。在 Next Play，我负责开发和测试 web 应用功能。这些经历说明我能实现交互系统、做评测，也有常规的软件测试经验。但我还没有一套针对 XR 原型、别人能直接安装并复现的测试包，这个经验我觉得需要补齐。

### AI-expanded version (previous row, condensed; for comparison only)

| Gap | Evidence the target demands it | What I have | Plan to close it |
| --- | --- | --- | --- |
| **G3 — Demonstrate XR testing and reproducible release.** | **J1** real-world deployment as the main signal; **J3** reinforces test execution, build/deployment workflows, and documentation, applied at prototype scope. | GazeCastGrasp (`proj-03`) and Next Play testing (`exp-03`) as a starting point; no XR installation and failure-handling test package. | Inspect existing tests and builds; check target selection, cancel/reset, stale input, and reconnection; record expected/actual results, version, and steps; separate automated from manual checks; begin robot-command failure cases in simulation or replay. **Close when:** another person can install that version, repeat the checks, and reconcile outcomes with recorded pass/fail status. |

### Contribution record

AI (ChatGPT) first proposed the test/release direction and example checks. I selected the gap and wrote the Chinese Gap/Plan/Close-when wording. For the Evidence and What-I-have columns, I reviewed a reference version from Claude and revised it. My first Evidence draft said of the Axon role "I think I can try for it"; Claude pointed out that this was a personal intention rather than demand evidence, and inconsistent with treating Axon as a senior, non-eligibility reference, so I changed it to "worth building early." I translated the Gap/Plan wording myself; Claude translated the other two columns and changed "Include both" to "Label which tests are automated and which are manual" to match my original "分别".

## Correction of the earlier G2

An earlier draft implied I lacked gaze/vision evaluation experience. I corrected it:

> 我做过眼动和视觉系统，对于整个系统而言，使用舒适性和系统准确性是一个很重要的测评指标。比如当系统测评通过对现实物体的预测准确性进行对比和失败情况就可以进行分析了。

*(English, AI-assisted: I have worked on gaze and vision systems. Comfort and system accuracy are important evaluation criteria; comparing prediction accuracy on real objects and analyzing failure cases supports system evaluation.)*

The current G2 therefore targets runtime timing and synchronization, not the accuracy evaluation I have already done.

## Completion status

All three deliverables can use one existing gaze/MR prototype, and existing records will be recovered before new work starts. When a gap's evidence exists, the corresponding entry is added to `resume.json` and the row is removed.
