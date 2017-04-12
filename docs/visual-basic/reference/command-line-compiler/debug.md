---
title: / Debug (Visual Basic) | Microsoft-Dokumentation
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
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
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
ms.openlocfilehash: 7384e69f066022e861a4277f418df3f4d094c3be
ms.lasthandoff: 03/13/2017

---
# <a name="debug-visual-basic"></a>/debug (Visual Basic)
Bewirkt, dass der Compiler Debuginformationen und platzieren Sie es in den Ausgabedateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Angeben von `+` oder `/debug` bewirkt, dass der Compiler Debuginformationen generiert und in einer PDB-Datei. Angeben von `-` hat dieselbe Wirkung wie die Angabe von nicht `/debug`.|  
|`full` &#124; `pdbonly`|Optional. Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Wenn Sie nicht angeben `/debug:pdbonly`, der Standardwert ist `full`, wodurch Sie einen Debugger an das ausgeführte Programm. Die `pdbonly` Argument ermöglicht das Debuggen von Quellcode, wenn das Programm im Debugger gestartet, es wird jedoch Assemblersprache Code nur, wenn das ausgeführte Programm an den Debugger angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um Debug-Builds zu erstellen. Wenn Sie keinen angeben `/debug`, `/debug+`, oder `/debug:full`, werden die Ausgabedatei des Programms nicht debuggen.  
  
 In der Standardeinstellung Debuginformationen nicht ausgegeben (`/debug-`). Geben Sie zum Ausgeben von Debuginformationen `/debug` oder `/debug+`.  
  
 Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](http://msdn.microsoft.com/library/7d90ea7a-150f-4f97-98a7-f9c26541b9a3).  
  
|Zum Festlegen von/Debug in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4.  Ändern Sie den Wert in der **Debuginfo generieren** Feld.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden Debuginformationen in die Ausgabedatei `App.exe`.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
