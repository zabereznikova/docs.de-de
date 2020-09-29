---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 7ded2b7d102430d8d4e545da5ab6ce8bafe3609e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095421"
---
# <a name="-recurse"></a>-recurse

Kompiliert Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  

 `dir`  
 Dies ist optional. Das Verzeichnis, in dem die Suche beginnen soll. Wenn nicht angegeben, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Erforderlich. Die Datei(en), nach der oder denen gesucht werden soll. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  

 Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne `-recurse` zu verwenden. Wird kein Name für die Ausgabedatei angegeben, verwendet der Compiler dafür die erste verarbeitete Eingabedatei. Dies ist in der Regel die erste Datei in der alphabetisch sortierten Liste der kompilierten Daten. Daher ist es sinnvoll, eine Ausgabedatei mithilfe der `-out`-Option anzugeben.  
  
> [!NOTE]
> Die Option `-recurse` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  

 Mit dem folgenden Befehl werden alle Visual Basic-Dateien im aktuellen Verzeichnis kompiliert:  
  
```console
vbc *.vb  
```  
  
 Mit dem folgenden Befehl werden alle Visual Basic-Dateien im Verzeichnis `Test\ABC` und alle Verzeichnisse darunter kompiliert und anschließend `Test.ABC.dll` generiert.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-out (Visual Basic)](out.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
