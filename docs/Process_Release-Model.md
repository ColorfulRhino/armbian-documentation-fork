## Rolling releases

Armbian provides automated daily rolling releases of [small selection of images](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml) for all supported targets. Images are available at respective board download pages: <https://www.armbian.com/download>. Armbian also populates its own packages repository so updates are available as an upgrade for existing installations.

## Point releases

Armbian runs "train" based point releases. Whatever is ready to board the train, does so. Whatever is not has to wait for the next train. This enables us to have a predictable release cycles making it easy to plan. It also puts the responsibility on developers to make sure they have features ready on time. 

Armbian releases quarterly at the end of **February, May, August, November**. Offset is because we all know that nothing happens for half of December. At the beginning of a release cycle, we have a planning meeting and **two weeks before the end of the release we freeze integration of new features**.

## Release Cycle

Releases last three months. Each release starts with a meeting for planning. After planning, developers and development teams build their deliverable using whatever methods (scrum, kanban, waterfall, ... ) they want but shall commit their code frequently, leading **up to the last 2 weeks**. The project does not accept "dumps" of code at the end. **Commit early and often** on master. Two weeks before the release date, we halt feature integration and only allow bug fixes. At some point during those two weeks, we start the release candidate process. This process starts by pulling a branch off master that will become the release branch. That frees up master for development on the next release. On the release candidate branch we work on bug fixes, and choose "release candidate", RC, tags. The software at that tag is a candidate for release, and it is submitted to automated and manual tests on real hardware. If automated tests are passing, we can officially tag it as the release. If it does not, we enter another bug fix cycle and create a new release candidate. We iterate until we have a candidate that can be the formal release. Usually, this takes 2-3 cycles and 1-3 weeks of time.

Development epics, stories and bugs for each release are tracked through [Jira](https://armbian.atlassian.net/).

## Release Branching, Versioning and Tags

Branches in Armbian follow this convention: 

 - **Main branch (main):** Main development will happen on the `main` branch. This is the latest and greatest branch, but is always "stable" and "deployable". All tests always pass on this branch.
 - **Release branch (v24.08 for example):** This is a branch per release with frozen external sources.
 
Each Armbian release will have the following version format:

**Format:** `<major>.<minor>.<revision>`

`<major>` and `<minor>` version are incremented at the end of the release cycles while `<revision>` is incremented for a fix.

## Release Naming

 
|version| codename | release month | work |
|:--|:--|:--|:--|
| 19.11 | Vaquita | November| [done](https://armbian.atlassian.net/projects/AR/versions/10000/tab/release-report-all-issues)
| 20.02 | Chiru | February| [done](https://armbian.atlassian.net/projects/AR/versions/10001/tab/release-report-all-issues)
| 20.05 | Kagu | May | [done](https://armbian.atlassian.net/projects/AR/versions/10002/tab/release-report-all-issues)
| 20.08 | Caple | August| [done](https://armbian.atlassian.net/projects/AR/versions/10003/tab/release-report-all-issues)
| 20.11 | Tamandua | November | [done](https://armbian.atlassian.net/projects/AR/versions/10004/tab/release-report-all-issues)
| 21.02 | Urubu | February | [done](https://armbian.atlassian.net/projects/AR/versions/10005/tab/release-report-all-issues)
| 21.05 | Jerboa | May | [done](https://armbian.atlassian.net/projects/AR/versions/10006/tab/release-report-all-issues)
| 21.08 | Caracal | August | [done](https://armbian.atlassian.net/projects/AR/versions/10007/tab/release-report-all-issues)
| 21.11 | Sambar | November | [cancelled](http://meeting.armbian.de/armbian.2021-10-16-14.01.txt)
| 22.02 | Pig | February | [done](https://armbian.atlassian.net/projects/AR/versions/10009/tab/release-report-all-issues)
| 22.05 | Jade | May | [done](https://armbian.atlassian.net/projects/AR/versions/10010/tab/release-report-all-issues)
| 22.08 | Yapok | August | [done](https://armbian.atlassian.net/projects/AR/versions/10011/tab/release-report-all-issues)
| 22.11 | Goral | November | [done](https://armbian.atlassian.net/projects/AR/versions/10012/tab/release-report-all-issues)
| 23.02 | Quoll | February | [done](https://armbian.atlassian.net/projects/AR/versions/10013/tab/release-report-all-issues)
| 23.05 | Suni | May | [done](https://armbian.atlassian.net/projects/AR/versions/10014/tab/release-report-all-issues)
| 23.08 | Colobus | August | [done](https://armbian.atlassian.net/projects/AR/versions/10015/tab/release-report-all-issues)
| 23.11 | Topi | November | [done](https://armbian.atlassian.net/projects/AR/versions/10016/tab/release-report-all-issues)
| 24.02 | Kereru | February | [done](https://armbian.atlassian.net/projects/AR/versions/10017/tab/release-report-all-issues)
| 24.05 | Havier | May |  [done](https://armbian.atlassian.net/projects/AR/versions/10018/tab/release-report-all-issues)
| 24.08 | Yelt | August | [done](https://armbian.atlassian.net/projects/AR/versions/10019/tab/release-report-all-issues)
| 24.11 | Stirk | August | planned
| 25.02 | Iiwi | August | planned
| 25.05 | Caiman | August | planned
| 25.08 | Dunnart | August | planned
| 25.11 | Brach | August | planned
| 26.02 | Goa | August | planned



 by [https://www.codenamegenerator.com](https://www.codenamegenerator.com) from unusual animals

<!---
## Release Planning

A release planning starts with an public IRC meeting where developers and interested users come together in **first Saturday, one month before the release month**. 

Dates for **2020**: 

 * [April 4th](https://freenode.irclog.whitequark.org/armbian/2020-04-04)
 * [July 4th](https://freenode.irclog.whitequark.org/armbian/2020-07-04)
 * [October 3rd](https://freenode.irclog.whitequark.org/armbian/2020-10-03)
 
 Dates for **2021**: 
 
 * January [2nd](https://freenode.irclog.whitequark.org/armbian/2021-01-02)
 * April [3rd](http://meeting.armbian.de/)
 * July [3rd](https://libera.irclog.whitequark.org/armbian/2021-07-10)
 * October [16th]

Dates for **2022**: 

 *  January [29th](http://meeting.armbian.de/armbian.2022-01-29-13.02.html)
 *  April [23th](http://meeting.armbian.de/armbian.2022-04-23-14.00.html)
 *  August [13th](http://meeting.armbian.de/armbian.2022-08-13-14.00.html)
 *  October (canceled)

Dates for **2023**:

 *  January [7th](http://meeting.armbian.de/armbian.2023-01-07-15.04.html)
 *  April [1st](http://meeting.armbian.de/armbian.2023-04-01-14.57.html)
 *  August (canceled)
 *  October 7th - no summary :(

Dates for **2024**:

 *  February [10th](http://meeting.armbian.de/armbian.2024-02-10-15.01.html)
 

### Agenda:

- 00:00 - 00:02 `#startmeeting Tamandua`: Meeting coordinator (MC) calls meeting to order. 
- 00:02 - 00:05 `#topic check-in`: MC gives control to participant to check-in and wait for latecomers. If your handle is not self explanatory, add your forum/github handle and just say hi.
- 00:05 - 00:07 `#topic late topics`: MC [points out to agenda](https://docs.armbian.com/Process_Release-Model/#release-planning) and asks if there is any late topic to add.
- 00:07 - 00:09 `#topic FYI`: Stuff to know beforehand - MC presents meeting relevant news and rules of engagement:
  - note #1: **IRC translator**: If your English is poor, simply write in your native language. Start your sentence with `--` at the beginning.
  - rule #1: When you get a voice, please *be quick and concise* (1-2 min) and make it clear when you stop. ("No more, I'm done")  
  - rule #2: If meeting is going out of desired agenda, MC will use *"STOP STOP STOP"*, wait to get attention and then proceed with the meeting agenda. **Please stop chatting and listen.**
  - rule #3: Please **highlight** important information appropriately by putting a keyword in front of your message: `#info` `#action` `#idea` `#help` check tips below.

- 00:09 - 00:30 **Board maintainers/development**: MC is calling out on by team sections as defined at GitHub
  - *Note:* tasks should be [tracked by Jira](https://armbian.atlassian.net/secure/RapidBoard.jspa?rapidView=2).
    If they are not there, please add them during or right after the meeting
  - *Note:* board maintainers present tasks, bugs or projects they are working on (open discussion for each section if possible, otherwise MC calls people out).
  - `#topic development Allwinner`
  - `#topic development Amlogic`
  - `#topic development Marvell`
  - `#topic development Rockchip`
  - `#topic development others`
- 00:30 - 00:40 **build system**
  - `#topic buildsystem enhancements`: [build script enhancements](https://armbian.atlassian.net/browse/AR-339?filter=10004)
  - `#topic buildsystem desktop`: [desktop and multimedia](https://armbian.atlassian.net/browse/AR-284?filter=10005)
- 00:40 - 00:45 **Infrastructure**
  - `#topic Infrastructure - Servers / CI`
  - `#topic Infrastructure - planned/unplanned changes on forums`
  - `#topic Infrastructure - IRC: new channel and pushes to commits`
- 00:45 - 00:50 `#topic Jira Backlog`: [**Cycle Jira backlog**](https://armbian.atlassian.net/browse/AR):
   - discuss task / bug (one at a time)
   - assign to person / release / tag
   - re-prioritise

- 00:50 - 00:55 `#topic open issues`
  - Check and cycle [open issues](https://github.com/armbian/build/issues) and [pull requests](https://github.com/armbian/build/pulls) on a build engine
- 00:55 - 00:56 `#topic board support status updates`
  - Discuss (last 10-15) board status update on download pages and build engine (wip, supported, eol) https://www.armbian.com/download/
- 00:56 - 00:57 `#topic release officer and meeting organizer and goverance`
  - Choose upcoming release officer and next meeting organizer (1 or 2 roles). We need someone that is not well acquiented with the process to see if our documentation is good enough. He will get full support / backup, so no need to worry about anything.
  - Check if [https://docs.armbian.com/Community_Governance/](https://docs.armbian.com/Community_Governance/) is up to date
- 00:57 - 1:00 `#topic questions about Jira usage`
  - Answer questions relating to [**how to use Jira**](https://docs.armbian.com/Process_Managing_Workflow/) (if any)
- 01:00 - `#topic misc / open discussion`

### Tips:

- channel is recorded so a summary and adjustments to Jira can made afterwards, ideally along with the meeting
- A *meetbot* will create a meeting summary at the end of the meeting. This however **heavily relys on user input**. So if you have important information to share please put a appropriate keyword in front of your message:
```
#info - Add an info item to the minutes. People should liberally use this for important things they say, so that they can be logged in the minutes.
#action - Document an action item in the minutes. Include any nicknames in the line, and the item will be assigned to them. (nicknames are case-sensitive)
#idea - Add an idea to the minutes.
#help - Add a "Call for Help" to the minutes. Use this command when you need to recruit someone to do a task.
```

Meeting location is IRC channel [#armbian](https://web.libera.chat/) on [Libera](https://libera.chat/). Meeting start times are announced in [Forum Events](https://forum.armbian.com/events/).
-->

## Release Coordinating

### Summary
A release starts as a RC branch cut from `main` at freeze time. Once a RC branch is cut, `main` can be unfrozen and development can continue. RC branch is a rolling release that accepts bug fixes. The bug fixes should be cherry-picked back to `main` branch. Once the RC is stable, a final release as a branch named after its version. A release is *never* merged to `main`. Once a release is complete, it only should be updated for severe bugs and security vulnerabilities. A release is only maintained until the next release.


### 1. Forum Communication

- Create a new thread in the [Armbian Project Administration forum](https://forum.armbian.com/forum/39-armbian-project-administration/)
  - Ex topic name: `Armbian 24.02 (Kereru) Release Thread`
- Tag the post with relase, release version, and codename
- Use the following template to begin the body of the release thread:

```
Release Candidate Code Freeze Date: YYYY-MM-DD
Release Date: YYYY-MM-DD
Release Candidate Branch Link: URL
Release Changelog: URL
Release Coordinator: @yourname
Testing Tracking Sheet: https://example.com/link  (google sheets)

The goal of this thread is to discuss testing, bugfixes, and the overall quality of the release.  Once the release is complete, this thread should be locked and unpinned. 
```
- Before Code Freeze -- Make note in the thread the incomplete Jira issues tagged for the release [example](https://forum.armbian.com/topic/12763-armbian-2002-chiru-release-thread/?tab=comments#comment-93245)
- After test images are procuded, engage in community for assistants wih testing.. forums, Twitter, etc.  [share this tool](https://github.com/armbian/autotests)

### 2. Release Candidate Branch Management

- For code freeze -- create a RC branch as `version-rc` ex: `v20.02.0-rc`
- If possible, create Jira tickets for major changes in github that were not tracked in Jira
- Begin testing process. See [Release Testing](#release-testing)
- Do not modify branch directy. Only accept PRs
- Only accept PRs for bug fixes. No features
- Update `main` branch version to the NEXT release version with `-trunk`  ex. If RC is v20.02.0-rc `main` becomes v20.05.0-trunk
- CI testing should pass on PR
- Test images should automatically be built via Igor's script
- Repeat build, test, and bugfix process until release is stable
- Cherry-pick bug fixes back into master
- Create Final release branch from RC

### 3. Release

- In Github create a release from final release branch
Enable [source freezing](https://github.com/armbian/build/pull/6318) for this branch
```
./compile.sh targets
cp output/info/git_sources.json config/sources/
```
following by commiting this code to build framework.
- Copy release notes generated by Jira release into Github form
- Add other appropriate information into release Github release notes
- Point Armbian build system to new release
- Update Armbian documentation to reflect current release
- Celebrate
