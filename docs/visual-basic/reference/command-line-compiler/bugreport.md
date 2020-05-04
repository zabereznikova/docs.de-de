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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793550"
---
# <a name="-bugreport"></a>-bugreport

Hiermit wird eine Datei erstellt, die Sie verwenden können, wenn Sie einen Fehlerbericht übermitteln.

## <a name="syntax"></a>Syntax

```console
-bugreport:file
```

## <a name="arguments"></a>Argumente

|Begriff|Definition|
|---|---|
|`file`|Erforderlich. Dies ist der Name der Datei, die Ihren Fehlerbericht enthalten soll. Wenn der Name ein Leerzeichen enthält, müssen Sie den Dateinamen in Anführungszeichen einschließen (" ").|

## <a name="remarks"></a>Hinweise

Die folgenden Informationen werden `file` hinzugefügt:

- Kopie aller Quellcodedateien in der Kompilierung

- Liste der bei der Kompilierung verwendeten Compileroptionen

- Versionsinformationen über den Compiler, die Common Language Runtime und das Betriebssystem

- Compilerausgabe, falls vorhanden.

- Beschreibung des gemeldeten Problems

- Beschreibung Ihres Vorschlags zur Beseitigung des gemeldeten Problems

Da in `file` Kopien von allen Quellcodedateien enthalten sind, sollten Sie den (vermuteten) Codefehler im möglichst kürzesten Programm reproduzieren.

> [!IMPORTANT]
> Mit der Option `-bugreport` wird eine Datei erstellt, die potenziell vertrauliche Informationen enthält. Dies umfasst die aktuelle Uhrzeit, Compilerversion, .NET Framework-Version, Betriebssystemversion, den Benutzernamen, die Befehlszeilenargumente zum Ausführen des Compilers, den gesamten Quellcode und die binäre Form einer Assembly, auf die verwiesen wird. Auf diese Option können Sie zugreifen, indem Sie in der Web.config-Datei Befehlszeilenoptionen für eine serverseitige Kompilierung einer ASP.NET-Anwendung angeben. Ändern Sie die Machine.config-Datei, um Benutzern das Kompilieren auf dem Server zu verbieten und dies zu verhindern.

Wenn diese Option mit `-errorreport:prompt`, `-errorreport:queue` oder `-errorreport:send` verwendet wird und die Anwendung einen internen Compilerfehler findet, werden die Informationen in `file` an die Microsoft Corporation gesendet. Diese Informationen helfen Microsoft-Entwicklern dabei, die Ursache des Fehlers zu ermitteln und die nächste Version von Visual Basic zu verbessern. Standardmäßig werden keine Informationen an Microsoft gesendet. Wenn Sie jedoch eine Anwendung mit `-errorreport:queue` kompilieren, die standardmäßig aktiviert ist, sammelt die Anwendung die Fehlerberichte. Wenn sich der Administrator des Computers dann anmeldet, zeigt das Fehlermeldungssystem ein Popupfenster an, mit dem der Administrator alle Fehlerberichte, die seit der Anmeldung aufgetreten sind, an Microsoft weiterleiten kann.

> [!NOTE]
> Die Option `-bugreport` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird *T2.vb* kompiliert, und alle Fehlerberichtinformationen werden in die Datei *Problem.txt* eingefügt.

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-debug (Visual Basic)](debug.md)
- [-errorreport](errorreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [trustLevel-Element für securityPolicy (ASP.NET-Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
