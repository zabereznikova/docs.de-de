---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 2617c42d7b176806cfac0fc2247760727608261a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775645"
---
# <a name="-keyfile"></a>-keyfile
Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```console 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Erforderlich. Die Datei, die den Schlüssel enthält. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen ("") einschließen.  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. Weitere Informationen finden Sie unter [Sn. exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Wenn Sie mit `-target:module` kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)kompilieren.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) an den Compiler übergeben. Verwenden Sie [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Microsoft Intermediate Language-Modul angeben.  
  
 Für den Fall, dass sowohl `-keyfile` als auch " [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) " angegeben werden (entweder über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut), versucht der Compiler zunächst, den Schlüssel Container zu erhalten. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn der Compiler den Schlüssel Container nicht findet, wird versucht, die mit `-keyfile` angegebene Datei zu suchen. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüssel Container installiert (ähnlich wie `sn -i`), sodass der Schlüssel Container bei der nächsten Kompilierung gültig ist.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen zum Signieren einer Assembly finden [Sie unter Erstellen und verwenden](../../../standard/assembly/create-use-strong-named.md) von Assemblys mit starkem Namen.  
  
> [!NOTE]
> Die `-keyfile`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
