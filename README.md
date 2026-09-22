# D7084E_XAI_Lab4

This lab focused on phishing detection and explaining the model decisions using a few different learning approaches.

I trained and compared a decision tree, logistic regression, full random forest, low-label random forest, semi-supervised forest, and self-supervised model. The full random forest performed best on the test set, with Macro-F1 around 0.965 and FAR around 0.037. The semi-supervised forest did not improve over the 5% labelled forest, since Macro-F1 dropped from 0.940 to 0.934 and FAR went up from 0.062 to 0.071. The self-supervised model did slightly outperform the low-label logistic regression, moving from 0.912 to 0.918 Macro-F1, but the gain was small.

For the explainability part, SHAP showed that google_index, page_rank, and nb_www were among the strongest indicators, which matches the idea that suspicious websites often have little or no search presence. The decision tree also split first on google_index, which is a sensible phishing clue from a security perspective. The self-supervised model picked up some similar signals, but it also emphasised URL-structure features more than the forests did.

So far, Part A and Part B are complete and the main results match the expected lab findings.
