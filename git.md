# Repository Management

### Unstable Main

Summary:
- All branches start from main
- All branches are merged to main with review and must merge with no conflicts
- Releases branched from master
- QA happens on release branch

```mermaid

gitGraph
   commit
   branch feature-1
   checkout feature-1
   commit
   commit
   checkout main 
   branch feature-2
   commit
   checkout main
   merge feature-1
   branch ticket-1
   checkout main
   merge feature-2 type: REVERSE
   checkout feature-2
   merge main
   commit
   checkout main
   checkout ticket-1
   commit
   checkout main
   merge feature-2
   checkout main
   merge ticket-1
   branch release-v1
   checkout release-v1
   commit
   checkout main
   branch fixup-1
   commit
   checkout main
   merge fixup-1
   checkout release-v1
   merge main tag: "v1"
   checkout release-v1
```
