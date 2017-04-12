---
title: / addmodule | Microsoft-Dokumentation
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
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 949962905ec933dc42301bf8c21654e73dbe2f70
ms.lasthandoff: 03/13/2017

---
# <a name="addmodule"></a>/addmodule
Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumente  
 `fileList`  
 Erforderlich. Durch Trennzeichen getrennte Liste von Dateien, die Metadaten enthalten, jedoch keine Assemblymanifeste enthalten. Dateinamen mit Leerzeichen sollten in Anführungszeichen eingeschlossen werden ("").  
  
## <a name="remarks"></a>Hinweise  
 Die Dateien von der `fileList` Parameter muss erstellt werden, mit der `/target:module` Option oder mit einem anderen Compiler entspricht `/target:module`.  
  
 Alle Module mit hinzugefügt `/addmodule` muss sich im gleichen Verzeichnis wie die Ausgabedatei zur Laufzeit. D. h. Sie können ein Modul in einem Verzeichnis zur Kompilierungszeit angeben, aber das Modul muss im Verzeichnis Anwendung zur Laufzeit. Wenn sie nicht der Fall ist, erhalten Sie eine <xref:System.TypeLoadException>Fehler.</xref:System.TypeLoadException>  
  
 Bei Angabe von (implizit oder explizit) alle[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) -Option als `/target:module` mit `/addmodule`, übergeben Sie an, Dateien `/addmodule` Teil der Assembly des Projekts. Eine Assembly muss eine Ausgabedatei ausführen, die eine oder mehrere Dateien mit hinzugefügt `/addmodule`.  
  
 Verwendung [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält.  
  
> [!NOTE]
>  Die `/addmodule` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt ein Modul.  
  
 [!code-vb[VbVbalrCompiler&#47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Der folgende Code importiert die Typen des Moduls.  
  
 [!code-vb[VbVbalrCompiler&#48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Beim Ausführen von `t1`, gibt es `802`.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
