---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956267"
---
# <a name="-recurse"></a>-recurse
Kompiliert Quell Code Dateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.  
  
## <a name="syntax"></a>Syntax  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  
 `dir`  
 Optional. Das Verzeichnis, in dem die Suche beginnen soll. Wenn kein Wert angegeben wird, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Erforderlich. Die Datei(en), nach der oder denen gesucht werden soll. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu `-recurse`kompilieren, ohne zu verwenden. Wenn kein Ausgabe Dateiname angegeben ist, wird der Name der Ausgabedatei von dem Compiler auf der ersten verarbeiteten Eingabedatei gespeichert. Dies ist im Allgemeinen die erste Datei in der Liste der Dateien, die bei der alphabetischen Anzeige kompiliert werden. Aus diesem Grund empfiehlt es sich, eine Ausgabedatei mit der `-out` -Option anzugeben.  
  
> [!NOTE]
> Die `-recurse` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert alle Visual Basic Dateien im aktuellen Verzeichnis.  
  
```console
vbc *.vb  
```  
  
 Mit dem folgenden Befehl werden alle Visual Basic Dateien im `Test\ABC` Verzeichnis und alle darunter liegenden Verzeichnisse kompiliert und generiert. `Test.ABC.dll`  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
