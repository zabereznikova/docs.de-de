---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 243583e55dcf278f951b813cca8384246d2d6db9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085229"
---
# <a name="-keycontainer"></a>-keycontainer

Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`container`|Erforderlich. Die Containerdatei, die den Schlüssel enthält. Wenn der Name ein Leerzeichen enthält, müssen Sie den Dateinamen in Anführungszeichen einschließen (" ").|  
  
## <a name="remarks"></a>Hinweise  

 Der Compiler erstellt eine teilbare Komponente, indem er einen öffentlichen Schlüssel in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. Die Option `-i` installiert das Schlüsselpaar im Container. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Wenn Sie mit der Option `-target:module` kompilieren, wird der Name der Schlüsseldatei im Modul gespeichert und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [-addmodule](addmodule.md) kompilieren.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](keyfile.md) an den Compiler übergeben. Verwenden Sie [-delaysign](delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Weitere Informationen zum Signieren von Assemblys finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md).  
  
> [!NOTE]
> Diese Option `-keycontainer` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  

 Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt einen Schlüsselcontainer an.  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [-keyfile](keyfile.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
