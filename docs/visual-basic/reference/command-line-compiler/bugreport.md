---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793550"
---
# <a name="-bugreport"></a>-bugreport

Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht melden.

## <a name="syntax"></a>Syntax

```console
-bugreport:file
```

## <a name="arguments"></a>Argumente

|Begriff|Definition|
|---|---|
|`file`|Erforderlich Der Name der Datei, in der der Fehlerbericht enthalten sein soll. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn der Name ein Leerzeichen enthält.|

## <a name="remarks"></a>Hinweise

Die folgenden Informationen werden `file`hinzugefügt:

- Eine Kopie aller Quell Code Dateien in der Kompilierung.

- Eine Liste der Compileroptionen, die in der Kompilierung verwendet werden.

- Versionsinformationen über den Compiler, Common Language Runtime und das Betriebssystem.

- Compilerausgabe, falls vorhanden.

- Eine Beschreibung des Problems, für das Sie dazu aufgefordert werden.

- Eine Beschreibung, wie Sie der Ansicht sind, dass das Problem behoben werden sollte, für das Sie dazu aufgefordert werden.

Da eine Kopie aller Quell Code Dateien in `file`enthalten ist, kann es ratsam sein, den (verdächtigen) Code Fehler in dem kürzesten Programm zu reproduzieren.

> [!IMPORTANT]
> Mit der Option `-bugreport` wird eine Datei erstellt, die potenziell vertrauliche Informationen enthält. Dies umfasst die aktuelle Uhrzeit, die Compilerversion, .NET Framework Version, die Betriebssystemversion, den Benutzernamen, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, den gesamten Quellcode und die binäre Form einer Assembly, auf die verwiesen wird. Auf diese Option können Sie zugreifen, indem Sie in der Datei Web. config Befehlszeilenoptionen für eine serverseitige Kompilierung einer ASP.NET-Anwendung angeben. Um dies zu verhindern, ändern Sie die Datei "Machine. config" so, dass Benutzer nicht auf dem Server kompiliert werden können.

Wenn diese Option mit `-errorreport:prompt`, `-errorreport:queue`oder `-errorreport:send`verwendet wird und die Anwendung auf einen internen Compilerfehler stößt, werden die Informationen in `file` an die Microsoft Corporation gesendet. Diese Informationen helfen Microsoft-Technikern dabei, die Ursache des Fehlers zu ermitteln, und können die nächste Version von Visual Basic verbessern. Standardmäßig werden keine Informationen an Microsoft gesendet. Wenn Sie jedoch eine Anwendung mit `-errorreport:queue`kompilieren, die standardmäßig aktiviert ist, sammelt die Anwendung Ihre Fehlerberichte. Wenn sich der Administrator des Computers anmeldet, zeigt das Fehler Berichterstattungs System ein Popup Fenster an, mit dem der Administrator alle Fehlerberichte, die seit der Anmeldung aufgetreten sind, an Microsoft weiterleiten kann.

> [!NOTE]
> Die `-bugreport`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird *T2. vb* kompiliert und alle Fehler Berichterstattungs Informationen in die Datei " *Problem. txt*" eingefügt.

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-Debug (Visual Basic)](debug.md)
- [-errorreport](errorreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [Trust Level-Element für securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
