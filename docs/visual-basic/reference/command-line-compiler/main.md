---
title: / main | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dded7621845141896f353d69ab757010c825b975
ms.lasthandoff: 03/13/2017

---
# <a name="main"></a>/main
Gibt die Klasse oder das Modul, enthält das `Sub Main` Verfahren.  
  
## <a name="syntax"></a>Syntax  
  
```  
/main:location  
```  
  
## <a name="arguments"></a>Argumente  
 `location`  
 Erforderlich. Eine vollständige Qualifizierung der Klasse oder des Moduls mit dem `Sub Main` Prozedur aufgerufen werden, wenn die Anwendung gestartet wird. Dies ist möglicherweise im Formular **/main:module** oder **Namespace.Module angegeben**.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, wenn Sie eine ausführbare Datei oder ein ausführbares Windows-Programm erstellen. Wenn die **/main** Option ausgelassen wird, wird der Compiler sucht nach einer gültigen gemeinsam genutzten `Sub Main` in allen öffentlichen Klassen und Modulen.  
  
 Finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) eine Erläuterung der verschiedenen Formen von der `Main` Verfahren.  
  
 Wenn `location` ist eine Klasse, die von erbt <xref:System.Windows.Forms.Form>, stellt der Compiler eine `Main` Prozedur, die die Anwendung gestartet wird, wenn die Klasse keine `Main` Verfahren.</xref:System.Windows.Forms.Form> Dadurch können Sie den Code in der Befehlszeile kompilieren, die in der Entwicklungsumgebung erstellt wurde.  
  
 [!code-vb[VbVbalrCompiler Nr.&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a>Zum Festlegen von/Main in Visual Studio integrierte Entwicklungsumgebung  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.  
  
     Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  Stellen Sie sicher, dass die **Anwendungsframework aktivieren** das Kontrollkästchen nicht aktiviert ist.  
  
4.  Ändern Sie den Wert in der **Startobjekt** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und `T3.vb`, angeben, die die `Sub Main` Prozedur befindet sich in der `Test2` Klasse.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: Visual Basic-Version von Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)   
 [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
