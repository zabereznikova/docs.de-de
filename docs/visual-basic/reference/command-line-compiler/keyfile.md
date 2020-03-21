---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266741"
---
# <a name="-keyfile"></a>-keyfile
Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Erforderlich. Datei, die den Schlüssel enthält. Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen (" ") ein.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert dann die endgliederische Assembly mit dem privaten Schlüssel. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. Weitere Informationen finden Sie unter [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Wenn Sie `-target:module`mit kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die beim Kompilieren einer Assembly mit [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)erstellt wird.  
  
 Sie können Ihre Verschlüsselungsinformationen auch mit [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)an den Compiler übergeben. Verwenden Sie [-delaysign,](../../../visual-basic/reference/command-line-compiler/delaysign.md) wenn Sie eine teilweise signierte Assembly wünschen.  
  
 Sie können diese Option auch als<xref:System.Reflection.AssemblyKeyFileAttribute>benutzerdefiniertes Attribut ( ) im Quellcode für jedes Microsoft-Zwischensprachmodul angeben.  
  
 Falls beide `-keyfile` und [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (entweder durch Befehlszeilenoption oder durch benutzerdefiniertes Attribut) in derselben Kompilierung angegeben werden, versucht der Compiler zuerst den Schlüsselcontainer. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn der Compiler den Schlüsselcontainer nicht findet, `-keyfile`versucht er die mit angegebene Datei. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer (ähnlich `sn -i`wie ) installiert, sodass bei der nächsten Kompilierung der Schlüsselcontainer gültig ist.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen zum Signieren einer Assembly finden Sie unter Erstellen und Verwenden von Assemblys mit [starkem Namen.](../../../standard/assembly/create-use-strong-named.md)  
  
> [!NOTE]
> Die `-keyfile` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur beim Kompilieren über die Befehlszeile verfügbar.

## <a name="example"></a>Beispiel

Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Weitere Informationen

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Referenz (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
