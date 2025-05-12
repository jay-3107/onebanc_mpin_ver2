# MPIN Security Validator : 
A comprehensive security tool for validating Mobile PIN strength in banking applications.

# Author: Jayesh Vilas Wankhede


# Overview : 
The MPIN Validator analyzes 4-digit and 6-digit PINs against common patterns and personal information to help users create stronger authentication credentials for mobile banking. Rather than providing simple pass/fail validation, it delivers specific weakness identification with detailed reason codes.

Problem Statement
Mobile banking security is compromised when users choose predictable PINs:

Sequential numbers (1234, 4321)
Repeated digits (1111, 9999)
Patterns based on birthdates or anniversaries
Keyboard patterns (2580, 1470)
Traditional validators fail to detect when users transform personal information into seemingly random combinations, creating a false sense of security.

Key Features
Analyzes both 4-digit and 6-digit PINs
Detects common PIN patterns algorithmically
Validates against demographic information (birth dates, anniversaries)
Identifies sophisticated transformations of personal data
Provides specific weakness categorization
Interactive command-line interface with color-coded output
Technical Implementation
Core Components
Code

┌───────────────────┐    ┌────────────────┐    ┌─────────────────┐
│ DateComponent     │    │ Pattern        │    │ Special Pattern │
│ Extractor         │───▶│ Generator      │───▶│ Detector        │
└───────────────────┘    └────────────────┘    └─────────────────┘
         │                       │                     │
         └───────────────────────▼─────────────────────┘
                               ┌─▼─┐
                               │   │
                               │   │
                               │   │
                               └─▲─┘
                                 │
                       ┌─────────────────┐
                       │ MPIN Validator  │
                       └─────────────────┘
DateComponentExtractor: Breaks dates into components for pattern analysis
PatternGenerator: Creates possible PIN patterns from demographic data
SpecialPatternDetector: Identifies complex transformation patterns
MPINValidator: Main validation engine and user interface
Usage
bash
python mpin_validator.py
The interactive mode guides users through:

Optional demographic information entry (birth dates, anniversaries)
PIN length selection (4 or 6 digits)
PIN entry and validation
Detailed strength assessment with specific weakness identification
Testing
Comprehensive test suite with 70 test cases covering:

Common PIN detection
Demographic pattern recognition
Keyboard pattern detection
Edge cases and complex transformations


Conclusion
The MPIN Validator significantly enhances mobile banking security by detecting PIN vulnerabilities beyond simple pattern matching. By providing specific feedback on weaknesses, it helps users create truly secure authentication credentials and addresses a critical gap in mobile financial security.