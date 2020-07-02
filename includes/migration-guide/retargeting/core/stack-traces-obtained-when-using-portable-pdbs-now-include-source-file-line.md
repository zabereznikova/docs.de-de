---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614534"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Stapelüberwachungen, die bei der Verwendung portabler PDBs abgerufen werden, enthalten nun Quelldatei- und Zeileninformationen, wenn diese angefordert werden

#### <a name="details"></a>Details

Ab .NET Framework 4.7.2 enthalten Stapelüberwachungen, die bei der Verwendung portabler PDBs abgerufen werden, nun Quelldatei- und Zeileninformationen, wenn diese angefordert werden. In Versionen vor .NET Framework 4.7.2 waren Quelldatei- und Zeileninformationen bei Verwendung portabler PDBs selbst dann nicht verfügbar, wenn diese explizit angefordert wurden.

#### <a name="suggestion"></a>Vorschlag

Für Anwendungen mit der Zielplattform .NET Framework 4.7.2 können Sie sich gegen Quelldatei- und Zeileninformationen entscheiden, wenn Sie portable PDBs verwenden, wenn diese nicht erwünscht sind, indem Sie Folgendes dem Abschnitt `<runtime>` Ihrer Datei „`app.config`“ hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

Bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.7.2 oder höher ausgeführt werden, können Sie Quelldatei- und Zeileninformationen bei der Verwendung portabler PDBs aktivieren, indem Sie Folgendes dem Abschnitt `<runtime>` der Datei „`app.config`“ hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
