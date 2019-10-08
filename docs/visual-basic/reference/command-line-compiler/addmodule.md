---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: fbe3634d1fbc03acd56ef7276d65fd54493b9806
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002413"
---
# <a name="-addmodule"></a>-addmodule
Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumente  
 `fileList`  
 Erforderlich. Eine durch Trennzeichen getrennte Liste von Dateien, die Metadaten enthalten, aber keine Assemblymanifeste enthalten. Dateinamen, die Leerzeichen enthalten, müssen in Anführungszeichen ("") eingeschlossen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die Dateien, die vom Parameter `fileList` aufgelistet werden, müssen mit der Option `-target:module` oder mit einem anderen Compiler `-target:module` erstellt werden.  
  
 Alle Module, die mit `-addmodule` hinzugefügt werden, müssen sich zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei befinden. Das heißt, Sie können zur Kompilierzeit ein Modul in einem beliebigen Verzeichnis angeben, das Modul muss sich jedoch zur Laufzeit im Anwendungsverzeichnis befinden. Wenn dies nicht der Fall ist, erhalten Sie den Fehler "<xref:System.TypeLoadException>".  
  
 Wenn Sie (implizit oder explizit) eine beliebige[Ziel Option (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) als `-target:module` mit `-addmodule` angeben, werden die Dateien, die Sie an `-addmodule` übergeben, Teil der Assembly des Projekts. Eine Assembly ist erforderlich, um eine Ausgabedatei auszuführen, der mindestens eine Datei mit `-addmodule` hinzugefügt wurde.  
  
 Verwenden Sie [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) , um Metadaten aus einer Datei zu importieren, die eine Assembly enthält.  
  
> [!NOTE]
> Die Option "`-addmodule`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird ein Modul erstellt.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Mit dem folgenden Code werden die Modultypen importiert.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Wenn Sie `t1` ausführen, wird `802` ausgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
