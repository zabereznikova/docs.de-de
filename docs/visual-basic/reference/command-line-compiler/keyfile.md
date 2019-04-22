---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: c13f34c23cad9c909c2c5bd3447f1a8fa53f9b4d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833312"
---
# <a name="-keyfile"></a>-keyfile
Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Erforderlich. Datei, die den Schlüssel enthält. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und klicken Sie dann die endgültige Assembly mit dem privaten Schlüssel signiert. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. Weitere Informationen finden Sie unter [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Bei der Kompilierung mit `-target:module`, der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly, die erstellt wird, wenn Sie eine Assembly mit integriert [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) an den Compiler übergeben. Verwenden Sie [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Sie können diese Option auch angeben, wie ein benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Microsoft intermediate Language-Modul.  
  
 Sowohl `-keyfile` und [- Keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) sind angegeben (entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut) in der gleichen Kompilierung, zuerst versucht der Compiler den Schlüsselcontainer. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn der Compiler den Schlüsselcontainer nicht findet, versucht es der angegebenen Datei, wobei `-keyfile`. Wenn dies erfolgreich ist, die Assembly mit den Informationen in der Schlüsseldatei signiert wird und die Schlüsselinformationen werden im Schlüsselcontainer installiert (ähnlich wie `sn -i`), damit bei der nächsten Kompilierung die Schlüsselcontainer gültig sein soll.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Finden Sie unter [erstellen und Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.  
  
> [!NOTE]
>  Die `-keyfile` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Referenz (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
