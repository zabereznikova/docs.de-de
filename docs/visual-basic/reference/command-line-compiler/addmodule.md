---
title: /addmodule
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fff292605e125776ae25e667d4813d770ed0a0aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="addmodule"></a>/addmodule
Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumente  
 `fileList`  
 Erforderlich. Durch Trennzeichen getrennte Liste der Dateien, die Metadaten enthalten, jedoch werden keine Assemblymanifeste. Dateinamen mit Leerzeichen sollten in Anführungszeichen eingeschlossen sein ("").  
  
## <a name="remarks"></a>Hinweise  
 Durch aufgelisteten Dateien der `fileList` Parameter muss erstellt werden, mit der `/target:module` -Option oder mit einem anderen Compiler entspricht `/target:module`.  
  
 Alle Module mit hinzugefügt `/addmodule` muss sich im selben Verzeichnis wie die Ausgabedatei zur Laufzeit. D. h. Sie können ein Modul in einem beliebigen Verzeichnis angeben, zum Zeitpunkt der Kompilierung, aber das Modul muss zur Laufzeit im Anwendungsverzeichnis sein. Wenn sie nicht der Fall ist, erhalten Sie eine <xref:System.TypeLoadException> Fehler.  
  
 Bei Angabe von (implizit oder explizit) alle[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option außer `/target:module` mit `/addmodule`, die Dateien, die Sie übergeben `/addmodule` werden Teil der Assembly des Projekts. Eine Assembly ist erforderlich, um eine Ausgabedatei ausführen, die einen oder mehrere Dateien hinzugefügt, mit `/addmodule`.  
  
 Verwendung [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält.  
  
> [!NOTE]
>  Die `/addmodule` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt ein Modul.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Im folgende Code werden die Typen des Moduls importiert.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Bei der Ausführung `t1`, gibt sie konsistent `802`.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
