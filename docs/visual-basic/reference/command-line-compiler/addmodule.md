---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 3e5c94cce8b16649854050855800ac1bf2fc6572
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580576"
---
# <a name="-addmodule"></a>-addmodule
Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, sämtliche Typinformationen aus den angegebenen Dateien bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumente  
 `fileList`  
 Erforderlich. Durch Trennzeichen getrennte Liste von Dateien, die Metadaten enthalten, aber Manifesten nicht enthalten. Dateinamen mit Leerzeichen müssen in Anführungszeichen eingeschlossen werden ("").  
  
## <a name="remarks"></a>Hinweise  
 Die Dateien sortiert nach der `fileList` Parameter muss erstellt werden, mit der `-target:module` Option oder mit einem anderen Compiler entspricht `-target:module`.  
  
 Alle Module mit hinzugefügten `-addmodule` zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei muss. D. h. Sie können ein Modul in einem Verzeichnis angeben, zum Zeitpunkt der Kompilierung, aber das Modul muss zur Laufzeit im Anwendungsverzeichnis sein. Wenn sie nicht der Fall ist, erhalten Sie eine <xref:System.TypeLoadException> Fehler.  
  
 Bei Angabe von (implizit oder explizit) alle[-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option, die nicht `-target:module` mit `-addmodule`, übergeben Sie an, Dateien `-addmodule` Teil der Assembly des Projekts. Eine Assembly ist erforderlich, um eine Ausgabedatei ausführen, die eine oder mehrere Dateien hinzugefügt, mit `-addmodule`.  
  
 Verwendung [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) um Metadaten aus einer Datei zu importieren, die eine Assembly enthält.  
  
> [!NOTE]
>  Die `-addmodule` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt ein Modul.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 Im folgende Code werden die Typen des Moduls importiert.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 Beim Ausführen von `t1`, es gibt `802`.  
  
## <a name="see-also"></a>Siehe auch
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Referenz (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
