# PR Format
- All PR's at Colonist follow a general structure as mentioned below; edit accordingly. A reviewer should be able to have all the information they require directly avaiable in the PR without having to go out and look for it themselves

```md
<!-- DELETE THE PARTS YOU DON'T USE -->
## Summary
* my_summary_pls

## Details
* edit_me_pls

## Testing
* explain_how_qa_should_test_this_PR
* list_edge_cases_qa_should_extra_pay_attention_to:
- [ ] edge_case_1
- [ ] edge_case_2
#### Platforms affected by this PR:  
- [ ] Web
- [ ] Mobile
  - [ ] Portrait
  - [ ] Landscape
- [ ] Discord
  - [ ] Browser
  - [ ] Desktop
  - [ ] Mobile

## References
<!-- LINK EVERY SINGLE RELATED ISSUE OR PR -->
* closes #
* [example_url](www.google.com)

## Checklists
<!-- DO NOT DELETE OR EDIT THIS LIST -->
- [ ] This PR abides by [Dev-lvl-1](../tree/development/docs/process/developer-level-1.md), [Dev-lvl-2](../tree/development/docs/process/developer-level-2.md) & [Dev-lvl-3](../tree/development/docs/process/developer-level-3.md) & [Coding Rules](../tree/development/docs/process/coding.md)
- [ ] Tested every affected platform in local (Frontend: Chrome, Safari, Firefox, Mobile)
- [ ] Written tests
- [ ] Added to patch notes according to the [guide](../tree/development/docs/process/developer-level-1.md#add-patch-note)
- [ ] I reviewed my own Pull Request commit by commit
- [ ] I didn't just select everything, this PR really does abide by these ^

## Screenshots
<!-- ANY UI RELATED CHANGE MUST HAVE SCREENSHOTS FOR ALL OF THESE -->

### Original
![image](original_img)

### Design
![image](design_img)

### Updated
![image](updated_img)

## Video (use Loom)
* show_every_scenario_this_PR_might_have_effected
```