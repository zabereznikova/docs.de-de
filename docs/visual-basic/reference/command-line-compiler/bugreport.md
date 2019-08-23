---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962446"
---
# <a name="-bugreport"></a>-bugreport
Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht melden.  
  
## <a name="syntax"></a>Syntax  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`file`|Erforderlich. Der Name der Datei, in der der Fehlerbericht enthalten sein soll. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn der Name ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Folgende Informationen werden hinzugefügt `file`:  
  
- Eine Kopie aller Quell Code Dateien in der Kompilierung.  
  
- Eine Liste der Compileroptionen, die in der Kompilierung verwendet werden.  
  
- Versionsinformationen über den Compiler, Common Language Runtime und das Betriebssystem.  
  
- Compilerausgabe, falls vorhanden.  
  
- Eine Beschreibung des Problems, für das Sie dazu aufgefordert werden.  
  
- Eine Beschreibung, wie Sie der Ansicht sind, dass das Problem behoben werden sollte, für das Sie dazu aufgefordert werden.  
  
 Da eine Kopie aller Quell Code Dateien in `file`enthalten ist, kann es ratsam sein, den (verdächtigen) Code Fehler in dem kürzesten Programm zu reproduzieren.  
  
> [!IMPORTANT]
> Mit `-bugreport` der-Option wird eine Datei erstellt, die potenziell vertrauliche Informationen enthält. Dies umfasst die aktuelle Uhrzeit, die Compilerversion, .NET Framework Version, die Betriebssystemversion, den Benutzernamen, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, den gesamten Quellcode und die binäre Form einer Assembly, auf die verwiesen wird. Auf diese Option können Sie zugreifen, indem Sie in der Datei Web. config Befehlszeilenoptionen für eine serverseitige Kompilierung einer ASP.NET-Anwendung angeben. Um dies zu verhindern, ändern Sie die Datei "Machine. config" so, dass Benutzer nicht auf dem Server kompiliert werden können.  
  
 Wenn diese Option `-errorreport:prompt`mit, `-errorreport:queue`oder `-errorreport:send`verwendet wird und die Anwendung auf einen internen Compilerfehler stößt, werden die Informationen `file` in an die Microsoft Corporation gesendet. Diese Informationen helfen Microsoft-Technikern dabei, die Ursache des Fehlers zu ermitteln, und können die nächste Version von Visual Basic verbessern. Standardmäßig werden keine Informationen an Microsoft gesendet. Wenn Sie jedoch eine Anwendung mithilfe `-errorreport:queue`von kompilieren, die standardmäßig aktiviert ist, sammelt die Anwendung Ihre Fehlerberichte. Wenn sich der Administrator des Computers anmeldet, zeigt das Fehler Berichterstattungs System ein Popup Fenster an, mit dem der Administrator alle Fehlerberichte, die seit der Anmeldung aufgetreten sind, an Microsoft weiterleiten kann.  
  
> [!NOTE]
> Die `/bugreport` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden alle `T2.vb` Fehler Berichterstattungs Informationen kompiliert und in die Datei `Problem.txt`eingefügt.  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Trust Level-Element für securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
