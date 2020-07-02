---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614503"
---
### <a name="serialport-background-thread-exceptions"></a>Ausnahmen in SerialPort-Hintergrundthreads

#### <a name="details"></a>Details

Mit <xref:System.IO.Ports.SerialPort>-Streams erstellte Hintergrundthreads beenden den Prozess nicht mehr, wenn Betriebssystemausnahmen ausgelöst werden. <br/>In Anwendungen, die auf .NET Framework 4.7 und frühere Versionen ausgelegt sind, wird ein Prozess beendet, wenn eine Betriebssystemausnahme in einem Hintergrundthread ausgelöst wird, der mit einem <xref:System.IO.Ports.SerialPort>-Stream erstellt wurde. <br/>In Anwendungen, die auf .NET Framework 4.7.1 oder eine höhere Version ausgelegt sind, warten Hintergrundthreads auf Betriebssystemereignisse im Zusammenhang mit der aktiven seriellen Schnittstelle und können in einigen Fällen abstürzen, z. B. beim plötzlichen Entfernen der seriellen Schnittstelle.

#### <a name="suggestion"></a>Vorschlag

Für Apps mit der Zielplattform .NET Framework 4.7.1 können Sie sich gegen die Ausnahmebehandlung entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes dem Abschnitt `<runtime>` Ihrer `app.config`-Datei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

Bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.7.1 oder höher ausgeführt werden, können Sie die Ausnahmebehandlung verwenden, indem Sie Folgendes dem Abschnitt `<runtime>` der `app.config`-Datei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
