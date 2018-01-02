---
title: /main
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5bb11bc62e951339113f4b48e98e05362490ca1
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="main"></a>/main
Gibt die Klasse oder das Modul mit dem Speicherort der `Sub Main`-Prozedur an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/main:location  
```  
  
## <a name="arguments"></a>Argumente  
 `location`  
 Erforderlich. Eine vollständige Qualifizierung der Klasse oder ein Modul mit der `Sub Main` Prozedur aufgerufen werden, wenn das Programm gestartet wird. Dies ist möglicherweise im Formular **/main:module** oder **Namespace.Module angegeben**.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen. Wenn die **/main** Option ausgelassen wird, wird der Compiler sucht nach einer gültigen gemeinsam genutzten `Sub Main` in alle öffentlichen Klassen und Module.  
  
 Finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) für eine Erläuterung zu den verschiedenen Formen von der `Main` Prozedur.  
  
 Wenn `location` ist eine Klasse, die von erben <xref:System.Windows.Forms.Form>, gibt der Compiler eine `Main` Prozedur, die die Anwendung gestartet wird, wenn die Klasse keine enthält `Main` Prozedur. Dadurch können Sie den Code über die Befehlszeile kompilieren, die in der Entwicklungsumgebung erstellt wurde.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a>Zum Festlegen von/Main in Visual Studio integrierte Entwicklungsumgebung  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
       
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  Stellen Sie sicher, dass die **Anwendungsframework aktivieren** das Kontrollkästchen nicht aktiviert ist.  
  
4.  Ändern Sie den Wert in der **Startobjekt** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und `T3.vb`, und geben, die die `Sub Main` Prozedur befinden sich der `Test2` Klasse.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
