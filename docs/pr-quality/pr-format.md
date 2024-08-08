# PR Format
- All PR's at Colonist follow a general structure as mentioned below; edit accordingly. A reviewer should be able to have all the information they require directly avaiable in the PR without having to go out and look for it themselves

```md
<!-- EDIT THE FOLLOWING -->
## Summary
* my_summary_pls

## Details
* edit_me_pls

## Testing
* explain_how_reviewer_should_test_this_PR
* list_edge_cases_to_pay_extra_attention_to:
- [ ] edge_case_1
- [ ] edge_case_2

#### Platforms affected by this PR:  
<!-- DO NOT DELETE OR EDIT THIS LIST -->
- [ ] Web
  - [ ] Full screen
  - [ ] Small screen

## References
<!-- LINK EVERY SINGLE RELATED ISSUE OR PR -->
* closes #
* [example_url](www.google.com)

## Checklists
<!-- DO NOT DELETE OR EDIT THIS LIST. ACTUALLY CHECKMARK WHAT YOU HAVE DONE -->
- [ ] This PR abides by the [fundamental](/docs/code-quality/fundamentals.md) and [intermediate](/docs/code-quality/intermediate.md) practices & [Coding Rules](/docs/code-quality/coding-rules.md)
- [ ] Tested every affected platform in local (Chrome, Safari, Firefox, Mobile)
- [ ] I reviewed my own Pull Request commit by commit
- [ ] I didn't just select everything, this PR really does abide by these ^

## Screenshots
<!-- ANY UI RELATED CHANGES MUST HAVE SCREENSHOTS -->

![image](updated_img)

## Video (use Loom; 1min max)
* show_every_scenario_this_PR_might_have_effected
```

## Examples
https://www.loom.com/share/00f1850cd8984e34849e990a669b6460