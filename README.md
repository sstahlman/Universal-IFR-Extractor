Universal IFR Extractor - MOD
=======================

Utility that can extract the internal forms representation from both EFI and UEFI modules and convert it into a human readable format.

This is an unofficial mod for Donovan6000's most excellent Universal-IFR-Extractor.

The specific part I needed was the Variable Store correlation, which Donovan wasn't displaying fully after parsing.  This branch goes further than
my pull request, and spits out a very verbose breakdown.  

**Original:**

```
0x3B8ED Form Set: Main {0E 24 43 D6 87 EC A4 EB B5 4B A1 E5 3F 3E 36 B2 0D A9 15 02 D0 04 00 00 00 00 00 00 00 00 01 00 00 00 9D 02}
0x3B911 Variable Store: 0xF009 {24 1B 61 DF E4 8B CA 93 D2 11 AA 0D 00 E0 98 03 2B 8C 09 F0 02 00 4C 61 6E 67 00}
0x3B92C 	Variable Store: 0xF00A {24 20 61 DF E4 8B CA 93 D2 11 AA 0D 00 E0 98 03 2B 8C 0A F0 02 00 4C 61 6E 67 43 6F 64 65 73 00}
0x3B94C 	Variable Store: 0xF000 {24 23 69 BB 70 E7 B4 BC 04 4D 9E 97 23 FF 94 56 FE AC 00 F0 01 00 53 79 73 74 65 6D 41 63 63 65 73 73 00}
0x3B96F 	Variable Store: 0x9 {24 27 43 D6 87 EC A4 EB B5 4B A1 E5 3F 3E 36 B2 0D A9 09 00 01 00 49 74 6B 4D 6F 64 69 66 69 65 64 53 65 74 75 70 00}
0x3B996 	Variable Store: 0xF015 {24 20 67 DE D0 3D D7 02 29 41 91 4A 9F 37 7C C3 4B 0D 15 F0 90 00 49 44 45 53 65 63 44 65 76 00}
0x3B9B6 	Form: Main, Form ID: 0x2 {01 06 02 00 15 02}
0x3B9BC 		Text: BIOS Version {03 0B 20 00 16 02 17 02 00 00 00}
```

**This MOD:**
```
0x3B8ED Form Set: Main {0E 24 43 D6 87 EC A4 EB B5 4B A1 E5 3F 3E 36 B2 0D A9 15 02 D0 04 00 00 00 00 00 00 00 00 01 00 00 00 9D 02}
0x3B911 Variable Store (27): {24 1B}
		 Name: [ Lang ] {4C 61 6E 67 00}
		 GUID: [ 8BE4DF61-93CA-11D2-AA0D-00E098032B8C ] {61 DF E4 8B CA 93 D2 11 AA 0D 00 E0 98 03 2B 8C}
		   ID: [ 0xF009 ] {09 F0}
		 Size: [ 002 ] {02 00}
0x3B92C Variable Store (32): {24 20}
		 Name: [ LangCodes ] {4C 61 6E 67 43 6F 64 65 73 00}
		 GUID: [ 8BE4DF61-93CA-11D2-AA0D-00E098032B8C ] {61 DF E4 8B CA 93 D2 11 AA 0D 00 E0 98 03 2B 8C}
		   ID: [ 0xF00A ] {0A F0}
		 Size: [ 002 ] {02 00}
0x3B94C Variable Store (35): {24 23}
		 Name: [ SystemAccess ] {53 79 73 74 65 6D 41 63 63 65 73 73 00}
		 GUID: [ E770BB69-BCB4-4D04-9E97-23FF9456FEAC ] {69 BB 70 E7 B4 BC 04 4D 9E 97 23 FF 94 56 FE AC}
		   ID: [ 0xF000 ] {00 F0}
		 Size: [ 001 ] {01 00}
0x3B96F Variable Store (39): {24 27}
		 Name: [ ItkModifiedSetup ] {49 74 6B 4D 6F 64 69 66 69 65 64 53 65 74 75 70 00}
		 GUID: [ EC87D643-EBA4-4BB5-A1E5-3F3E36B20DA9 ] {43 D6 87 EC A4 EB B5 4B A1 E5 3F 3E 36 B2 0D A9}
		   ID: [ 0x0009 ] {09 00}
		 Size: [ 001 ] {01 00}
0x3B996 Variable Store (32): {24 20}
		 Name: [ IDESecDev ] {49 44 45 53 65 63 44 65 76 00}
		 GUID: [ 3DD0DE67-02D7-4129-914A-9F377CC34B0D ] {67 DE D0 3D D7 02 29 41 91 4A 9F 37 7C C3 4B 0D}
		   ID: [ 0xF015 ] {15 F0}
		 Size: [ 144 ] {90 00}
0x3B9B6 	Form: Main, Form ID: 0x2 {01 06 02 00 15 02}
0x3B9BC 		Text: BIOS Version {03 0B 20 00 16 02 17 02 00 00 00}
```