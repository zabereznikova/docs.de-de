---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: e1e636da1d277f80f58268b24b69802006eb8315
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966280"
---
# <a name="-main"></a>-main
Gibt die Klasse oder das Modul mit dem Speicherort der `Sub Main`-Prozedur an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-main:location  
```  
  
## <a name="arguments"></a>Argumente  
 `location`  
 Erforderlich. Der Name der Klasse oder Modul, enthält die `Sub Main` Prozedur aufgerufen werden, wenn das Programm gestartet wird. Dies ist möglicherweise im Formular **-Main: Module** oder **-main:namespace.module**.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen. Wenn die **-main** Option ausgelassen wird, wird der Compiler sucht nach einer gültigen gemeinsam genutzten `Sub Main` in allen öffentlichen Klassen und Modulen.  
  
 Finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) eine Erläuterung der verschiedenen Formen von der `Main` Verfahren.  
  
 Wenn `location` ist eine Klasse, die von erbt <xref:System.Windows.Forms.Form>, der Compiler stellt eine Standardimplementierung `Main` Prozedur, die die Anwendung gestartet wird, wenn die Klasse keine `Main` Verfahren. Dadurch können Sie den Code in der Befehlszeile kompilieren, die in der Entwicklungsumgebung erstellt wurde.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>-Main in der integrierten Entwicklungsumgebung von Visual Studio festlegen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  Stellen Sie sicher, dass die **Anwendungsframework aktivieren** das Kontrollkästchen nicht aktiviert ist.  
  
4.  Ändern Sie den Wert in der **Startobjekt** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und `T3.vb`, geben Sie dabei, die die `Sub Main` Prozedur befindet sich in der `Test2` Klasse.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Siehe auch
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
