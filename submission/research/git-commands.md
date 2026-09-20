# Git Commands – Explained in Arabic with Real-World Scenarios

## git squash
تجمع كذا commit صغيرة في commit واحدة نضيفة.

**Scenario:** عملت 5 commits أثناء تطوير Feature، وقبل الـ Pull Request عايز تخليهم commit واحدة.

**Command:**
```
git rebase -i HEAD~5
```

---

## git merge
تدمج branch كامل في branch تاني وتحافظ على الـ history.

**Scenario:** خلصت feature/login وعايز تدخلها في main.

**Command:**
```
git checkout main
git merge feature/login
```

---

## git rebase
تحط commits الـ branch بتاعتك فوق آخر تحديث من branch تاني، وبتخلي الـ history خطي.

**Scenario:** main اتحدث وإنت لسه شغال على feature، فعايز تحدث الـ feature قبل الـ Pull Request.

**Command:**
```
git checkout feature
git rebase main
```

---

## git help
تجيب الـ documentation والـ options الخاصة بأي Git command.

**Scenario:** مش فاكر options بتاعة rebase.

**Command:**
```
git help rebase
```

---

## git cherry-pick
تاخد commit معينة من branch وتنقلها لـ branch تاني من غير ما تاخد باقي الـ commits.

**Scenario:** عندك bug fix مهم في feature، لكن باقي الـ feature مش جاهز للـ production.

**Command:**
```
git cherry-pick abc123
```

---

## git clean
تمسح الملفات الـ untracked من الـ working directory.

**Scenario:** عندك temporary أو generated files كتير ومش محتاجها.

**Command:**
```
git clean -n   # preview
git clean -f   # delete
```

---

## git grep
تدور على كلمة أو code داخل ملفات المشروع.

**Scenario:** عايز تعرف كل الأماكن اللي فيها CalculateSalary.

**Command:**
```
git grep "CalculateSalary"
```

---

## git blame
تعرف مين آخر واحد عدّل كل سطر في ملف.

**Scenario:** لقيت سطر غريب وعايز تعرف مين عدله وفي أي commit.

**Command:**
```
git blame Program.cs
```

---

## git bisect
تحدد أنهي commit هي اللي دخلت الـ bug.

**Scenario:** الكود كان شغال من فترة وباظ، ومش عارف أنهي commit سببت المشكلة.

**Command:**
```
git bisect start
git bisect good
git bisect bad
```

---

## git shortlog
تلخص الـ commits حسب كل developer.

**Scenario:** عايز تعرف كل developer عمل كام commit.

**Command:**
```
git shortlog -sn
```

---

## git prune
تنضف Git objects القديمة اللي مبقاش ليها reference.

**Scenario:** بعد عمليات زي reset أو rebase بقى فيه objects مش reachable من أي branch أو tag.

**Command:**
```
git prune
```

---

## git worktree
تشتغل على أكتر من branch في نفس الوقت في فولدرات مختلفة.

**Scenario:** إنت شغال على Feature وفجأة ظهر production bug؛ تعمل worktree للـ hotfix بدل ما تعمل stash وتبدل branch.

**Command:**
```
git worktree add ../hotfix hotfix
```

---

## git verify-commit
تتأكد إن الـ commit عليها signature صحيحة.

**Scenario:** الشركة بتطلب signed commits وعايز تتحقق من commit معينة.

**Command:**
```
git verify-commit abc123
```

---

## git filter-repo
تعدل أو تنضف الـ Git history بالكامل.

**Scenario:** Secret أو ملف كبير دخل الـ repository من زمان وعايز تشيله من الـ history كله.

**Command:**
```
git filter-repo --path file.txt --invert-paths
```
