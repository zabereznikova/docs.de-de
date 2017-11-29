---
title: XamlName-Grammatik
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 92327c8ff6232e64bf8b6b2a9d78e4a9eb30f3e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xamlname-grammar"></a>XamlName-Grammatik
XamlName-Grammatik ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die hier der Einfachheit halber reproduziert werden.  
  
## <a name="from-the-xaml-specification"></a>Von der Verwendung von XAML-Spezifikation  
 Die [MS-XAML]-Spezifikation definiert die XamlName-Grammatik zur Kennzeichnung der Gruppe der zulässigen symbolischen Bezeichner für Typen und Eigenschaften.  
  
 Zeichenfolgenwerte des Typs XamlName muss in der folgenden Grammatik entsprechen:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 Die folgenden allgemeinen Kategoriewerte davon ausgeht, gemäß der Definition in der Datenbank der Unicode-Zeichen  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML-Code definiert eine zweite Grammatik, DottedXamlName, für die Eigenschaft verwendeten und Ereignis Verweise und auch für angefügte Member an. Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Zeichenfolgenwerte des Typs DottedXamlName muss in der folgenden Grammatik entsprechen:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a>Hinweise  
 Die vollständige Spezifikation finden Sie unter [ \[MS-XAML-\]](http://go.microsoft.com/fwlink/?LinkId=114525).
