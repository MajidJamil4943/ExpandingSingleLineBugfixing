# 📘 ExpandingSingleLineBugfixing

## 🔍 Overview

ExpandingSingleLineBugfixing is a curated and richly annotated dataset of single-line bug-fixing commits across multiple open-source software projects, specifically in Java and Python. Each bug-fix instance in the dataset is associated with its patch, and for Java cases, a corresponding triggering test case is also included. These test cases are generated automatically and designed to fail on buggy code and pass on the fixed code, making them ideal for mutation testing, automated repair, fault localization, and software quality research.

This repository serves as a comprehensive resource for software engineering researchers, developers, and ML practitioners who need real-world, reproducible, and verifiable examples of bug-fixing behavior for their academic or industrial work.

## 🎯 Purpose

The main objectives of this repository are:

    •	To provide a clean, filtered collection of real-world single-line bug fixes from large-scale open-source projects.
    •	To support the automated generation of triggering test cases for those bugs using LLMs (e.g., DeepSeek-Chat).
    •	To promote reproducible research in the fields of mutation testing, automated debugging, and program repair.
    •	To serve as a benchmark dataset for training and evaluating ML models for software quality assurance.
    •	To help developers and researchers understand and simulate semantic and behavioral changes caused by minimal code edits.

## 🧪 Contents

The repository's datasets divided into the following:
    
    •  commit_id
    •  commit_url
    •  commit_message
    •  buggy_code
    •  fixed_code
    •  patch
    •  triggering_test_case

triggering_test_case ✅ (auto-generated using DeepSeek API)
These test cases demonstrate the expected behavioral change, enabling effective mutation testing and regression verification.


## 🧠 Motivation

Many existing datasets in software engineering focus on multi-line patches or large diff-based bug fix repositories. However:

    🟡 Single-line bugs are highly frequent in real-world software systems and often indicate subtle logic, typo, or semantic issues.
    🟡 Fine-grained bug repositories are rare but necessary for developing token-level or AST-level ML models.
    🟡 Most benchmarks lack test cases that demonstrate the behavioral difference between buggy and fixed code.

To bridge this gap, this repository aims to build a standard, verifiable, and public dataset of fine-grained bug fixes, complete with machine-generated test cases and structured metadata.


## 🛠️ My Contribution as a Software Engineering(Machine Learning) Researcher

As the creator of this repository, my contributions include:

    🔍 Mining and filtering thousands of Java and Python single line bug-fix commits from real-world repositories.
    ✅ Ensuring single-line patch integrity by verifying that each commit modifies only one line semantically.
    🤖 Using LLM APIs (DeepSeek-Chat) to generate JUnit and PyTest triggering test cases that:
    
      •  Fail on buggy code.
      •  Pass on the fixed version.
      •  Highlight the behavioral or exception change.
    
    🧪 Manually validating test cases and fixing compilation errors when necessary.
    🗃️ Structuring the dataset in a machine-readable JSON format for easy consumption in downstream tools and ML pipelines.
    🔁 Integrating this process into a semi-automated pipeline to encourage continuous expansion of the dataset.
    

## 📈 Use Cases

This repository is ideal for:

    🔬 Mutation Testing: Validating whether a test case can detect code mutations.
    
    🧠 Machine Learning: Training models for bug prediction, fix generation, or patch classification.
    
    🧪 Program Repair: Testing APR (Automated Program Repair) tools against reproducible bugs and fixes.
    
    👨‍💻 Developer Education: Teaching software debugging and testing concepts using real-world examples.
    
    🔍 Patch Impact Analysis: Understanding semantic vs. syntactic code changes and their effects.
    

## 🔄 Example Record (Java)

```json
  {
  "commit_id": "abc123",
  "commit_message": "Fix NPE in service initialization",
  "buggy_code": "if (config != null && config.isEnabled()) {",
  "fixed_code": "if (config != null && config.getFeature() != null && config.getFeature().isEnabled()) {",
  "patch": [
    "-if (config != null && config.isEnabled()) {",
    "+if (config != null && config.getFeature() != null && config.getFeature().isEnabled()) {"
  ],
  "TEST_CASE": "import static org.junit.Assert.*; ..."
  }
```


## 🧑‍🔬 Acknowledgements

    🔬 Built as part of master's research at Beijing Institute of Technology, School of Computer Science and Information Technology.
    
    ⚙️ LLM-based generation powered by DeepSeek-Chat API.
    
    ❤️ Inspired by existing datasets like Defects4J and jenkins but with a focus on fine-grained single-line bug fixes.
    

## 📢 How to Cite

If you use this dataset in your research or tooling:

    @misc{expandingSingleLineBugfixing4943,
    author = {Majid Jamil},
    title = {ExpandingSingleLineBugfixing: A Dataset of Real-World Single-Line Bug Fixes and Triggering Test Cases},
    year = {2025},
    howpublished = {\url{https://github.com/majidjamil/ExpandingSingleLineBugfixing}}
    }


## 📬 Contact

    For issues, collaborations, or contributions:
    
    GitHub: https://github.com/MajidJamil4943
    
    Email: majidjamil4943@gmail.com
    
