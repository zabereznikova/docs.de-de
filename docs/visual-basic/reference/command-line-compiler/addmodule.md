---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 9e8146497d63d949f138d6cd08c9ea8c7b03c651
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414310"
---
# <a name="-addmodule"></a>-addmodule
Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumente  
 `fileList`  
 Erforderlich. Eine durch Trennzeichen getrennte Liste mit Dateien, die Metadaten enthalten, jedoch keine Assemblymanifeste. Dateinamen, die Leerzeichen enthalten, müssen in Anführungszeichen ("") eingeschlossen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die durch den `fileList`-Parameter aufgelisteten Dateien müssen mit der Option `-target:module` oder einer entsprechenden Option eines anderen Compilers erstellt werden.  
  
 Alle mit `-addmodule` hinzugefügten Module müssen sich zur Laufzeit im selben Verzeichnis wie die Ausgabedatei befinden. Das bedeutet, dass Sie zur Kompilierzeit ein Modul in einem beliebigen Verzeichnis angeben können, sich das Modul zur Laufzeit jedoch im Anwendungsverzeichnis befinden muss. Andernfalls wird ein <xref:System.TypeLoadException>-Fehler angezeigt.  
  
 Wenn Sie mit `-addmodule` (implizit oder explizit) eine andere [-target (Visual Basic)](target.md)-Option als `-target:module` angeben, werden die Dateien, die Sie an `-addmodule` übergeben, Teil der Assembly des Projekts. Eine Assembly ist zum Ausführen einer Ausgabedatei erforderlich, die mindestens eine mit `-addmodule` hinzugefügte Datei enthält.  
  
 Verwenden Sie zum Importieren von Metadaten aus einer Datei, die eine Assembly enthält, die Option [-reference (Visual Basic)](reference.md).  
  
> [!NOTE]
> Die Option `-addmodule` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird ein Modul erstellt:  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Mit dem folgenden Code werden die Modultypen importiert:  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Wenn Sie `t1` ausführen, wird `802` ausgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-target (Visual Basic)](target.md)
- [-reference (Visual Basic)](reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
