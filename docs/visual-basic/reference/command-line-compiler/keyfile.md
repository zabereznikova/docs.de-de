---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: c81486243195f7d022bd474ef6db20d069b3a018
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085151"
---
# <a name="-keyfile"></a>-keyfile

Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  

 `file`  
 Erforderlich. Die Datei, die den Schlüssel enthält. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.  
  
## <a name="remarks"></a>Hinweise  

 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Wenn Sie mit der Option `-target:module` kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [-addmodule](addmodule.md) kompilieren.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](keycontainer.md) an den Compiler übergeben. Verwenden Sie [-delaysign](delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.  
  
 Wenn für die gleiche Kompilierung sowohl `-keyfile` als auch [-keycontainer](keycontainer.md) angegeben werden (über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut), versucht der Compiler zunächst, den Schlüsselcontainer zu verwenden. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn den Compiler den Schlüsselcontainer nicht findet, versucht er, die mit `-keyfile` angegebene Datei zu verwenden. Wenn dieser Vorgang erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert (vergleichbar mit `sn -i`), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen zum Signieren von Assemblys finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md).  
  
> [!NOTE]
> Die Option `-keyfile` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [-reference (Visual Basic)](reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
