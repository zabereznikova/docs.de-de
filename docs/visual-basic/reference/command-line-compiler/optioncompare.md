---
title: "/optioncompare | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optioncompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "optioncompare compiler option [Visual Basic]"
  - "-optioncompare compiler option [Visual Basic]"
  - "/optioncompare compiler option [Visual Basic]"
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /optioncompare
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.  
  
## Syntax  
  
```  
/optioncompare:{binary | text}  
```  
  
## Hinweise  
 Sie können `/optioncompare` auf zweierlei Weise angeben: als `/optioncompare:binary` zur Verwendung von binären Zeichenfolgenvergleichen und als `/optioncompare:text` zur Verwendung von Textzeichenfolgenvergleichen.  Standardmäßig verwendet der Compiler `/optioncompare:binary`.  
  
 In Microsoft Windows bestimmt die verwendete Codepage die binäre Sortierreihenfolge.  Eine typische binäre Sortierreihenfolge sieht folgendermaßen aus:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Bei textbasierten Zeichenfolgenvergleichen wird die Textsortierreihenfolge ohne Beachtung der Groß\-\/Kleinschreibung zugrunde gelegt, die das Gebietsschema des Systems vorgibt.  Eine typische Textsortierreihenfolge sieht folgendermaßen aus:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### So legen Sie \/optioncompare in der Visual Studio\-IDE fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Ändern Sie den Wert im Feld **Option Compare**.  
  
### So legen Sie \/optioncompare programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## Beispiel  
 Mit dem folgenden Code wird `rojFile.vb` kompiliert und ein Vergleich binärer Zeichenfolgen durchgeführt.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [VB\-Standard, Projekte, Dialogfeld "Optionen"](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)