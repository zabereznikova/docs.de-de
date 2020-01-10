---
title: Sicherheit und Benutzereingaben
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
ms.openlocfilehash: 0d34b06b44241feb7d6e3c8f76447b861563cfdc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705859"
---
# <a name="security-and-user-input"></a>Sicherheit und Benutzereingaben

Benutzerdaten, bei denen es sich um beliebige Eingaben handeln kann (Daten aus einer Webanforderung oder einer URL, Eingaben in Steuerelemente einer Microsoft Windows Forms-Anwendung usw.), können Code beeinträchtigen, da diese Daten häufig direkt als Parameter zum Aufrufen von anderem Code verwendet werden. Diese Situation ähnelt einem Angriff durch bösartigen Code, der Ihren Code mit ungewöhnlichen Parametern aufruft, weshalb dieselben Vorsichtsmaßnahmen ergriffen werden sollten. Die Sicherheit bei Benutzereingaben ist sogar schwieriger zu gewährleisten, da kein Stapelrahmen zum Verfolgen der möglicherweise nicht vertrauenswürdigen Daten vorhanden ist.

Diese Sicherheitslücken sind am schwierigsten zu finden, denn obwohl sie sich in Code befinden können, der mit der Sicherheit scheinbar nichts zu tun hat, sind sie dennoch ein Einfallstor für die Übergabe bösartiger Daten an anderen Code. Um diese Fehler aufzuspüren, verfolgen Sie alle Arten von Eingabedaten, schätzen Sie den Bereich möglicher Werte ein, und ermitteln Sie, ob der Code, der Zugriff auf diese Daten hat, alle diese Fälle behandeln kann. Sie können diese Fehler beheben, indem Sie Bereiche überprüfen und sämtliche Eingaben zurückweisen, die vom Code nicht behandelt werden können.

Im Folgenden sind einige wichtige Überlegungen zu Benutzerdaten aufgeführt:

- Alle Benutzerdaten in einer Serverantwort werden auf dem Client im Kontext der Site des Servers. Wenn der Webserver Benutzerdaten empfängt und diese in die zurückgegebene Webseite einfügt, können die Daten beispielsweise ein **\<script>** -Tag enthalten und so ausgeführt werden, als stammten sie vom Server.

- Beachten Sie, dass der Client beliebige URLs anfordern kann.

- Berücksichtigen Sie komplizierte oder ungültige Pfade:

  - .. \, äußerst lange Pfade

  - Verwendung von Platzhalterzeichen (*)

  - Tokenerweiterung (%token%)

  - Ungewöhnliche Formen von Pfaden mit besonderer Bedeutung

  - Alternative Streamnamen des Dateisystems, z. B. `filename::$DATA`

  - Kurze Versionen von Dateinamen, z. B. `longfi~1` für `longfilename`

- Denken Sie daran, dass durch Eval(userdata) jede Aktion ausgeführt werden kann.

- Seien Sie vorsichtig bei später Bindung an einen Namen, der Benutzerdaten enthält.

- Wenn Sie mit Webdaten arbeiten, müssen die unterschiedlichen Formen von Escapesequenzen berücksichtigen, die zulässig sind:

  - Hexadezimale Escapesequenzen (%nn)

  - Unicode-Escapesequenzen (%nnn)

  - UTF-8-Escapesequenzen mit Überlänge (%nn%nn)

  - Doppelte Escapesequenzen (%nn wird zu %mmnn, wobei %mm die Escapesequenz für „%“ ist)

- Besondere Vorsicht ist bei Benutzernamen geboten, die mehrere kanonische Formen haben können. Beispielsweise können Sie häufig entweder die Form MYDOMAIN\\*Benutzername* oder die Form *Benutzername*@mydomain.example.com verwenden.

## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
