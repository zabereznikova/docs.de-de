---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: 524660fca7c56fa490cc85169898bf2bf6d1a16e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400577"
---
# <a name="-optioninfer"></a>-optioninfer
Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Geben Sie `-optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `-optioninfer-` zu blockieren. Die `-optioninfer` -Option ohne angegebenen Wert entspricht dem `-optioninfer+`. Der Standardwert, wenn die `-optioninfer` Switch nicht vorhanden ist, ist auch `-optioninfer+`. Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.|  
  
> [!NOTE]
> Sie können die `-noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten. Der Compilerstandardwert für diese Option ist `-optioninfer-`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Quellcodedatei eine [Option Infer-Anweisung](../../language-reference/statements/option-infer-statement.md) enthält, überschreibt die Anweisung die Einstellung des `-optioninfer`-Befehlszeilencompilers.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>Festlegen von -optioninfer in der Visual Studio-IDE  
  
1. Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Ändern Sie auf der Registerkarte **Kompilieren** den Wert im Feld **Option infer**.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-optioncompare](optioncompare.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [Option Infer-Anweisung](../../language-reference/statements/option-infer-statement.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [-noconfig](noconfig.md)
- [Erstellen von der Befehlszeile aus](building-from-the-command-line.md)
