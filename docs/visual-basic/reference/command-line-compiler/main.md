---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005506"
---
# <a name="-main"></a>-main
Gibt die Klasse oder das Modul mit dem Speicherort der `Sub Main`-Prozedur an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>Argumente  
 `location`  
 Erforderlich. Der Name der Klasse oder des Moduls mit der `Sub Main`-Prozedur, die beim Programmstart aufgerufen werden soll. Dieser kann als **-main:module** oder **-main:namespace.module** vorliegen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Option ist geeignet, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen. Wird die Option **-main** nicht angegeben, sucht der Compiler in allen öffentlichen Klassen und Modulen nach einer gültigen freigegebenen `Sub Main`-Prozedur.  
  
 Informationen zu den verschiedenen Formularen der `Main`-Prozedur finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
 Ist `location` eine Klasse, die von <xref:System.Windows.Forms.Form> erbt, stellt der Compiler eine `Main`-Standardprozedur bereit, mit der die Anwendung gestartet wird, wenn die Klasse keine `Main`-Prozedur enthält. Auf diese Weise können Sie Code in der Befehlszeile kompilieren, der in der Entwicklungsumgebung erstellt wurde.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>So legen Sie „-main“ in der integrierten Visual Studio-Entwicklungsumgebung fest  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Anwendung** .  
  
3. Stellen Sie sicher, dass das Kontrollkästchen bei **Anwendungsframework aktivieren** nicht aktiviert ist.  
  
4. Ändern Sie die den Wert im Feld **Startobjekt**.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code werden `T2.vb` und `T3.vb` kompiliert. Dabei wird angegeben, dass sich die `Sub Main`-Prozedur in der `Test2`-Klasse befindet.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
