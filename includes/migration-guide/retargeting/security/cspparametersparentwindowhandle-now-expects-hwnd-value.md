---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614514"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle erwartet nun einen HWND-Wert

#### <a name="details"></a>Details

Der <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>-Wert, der in .NET Framework 2.0 eingeführt wurde, ermöglicht einer Anwendung die Registrierung eines Handlewerts für das übergeordnete Fenster, sodass jedes Benutzeroberflächenelement, das auf den Schlüssel zugreifen muss (wie etwa eine PIN-Eingabeaufforderung oder ein Zustimmungsdialogfeld), als untergeordnetes modales Fenster des angegebenen Fensters geöffnet wird. Für eine Windows Forms-App, deren Zielplattform .NET Framework 4.7 oder höher ist, kann die Eigenschaft <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> beispielsweise mit dem folgenden Code festgelegt werden:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

In früheren Versionen von .NET Framework wurde erwartet, dass der Wert ein <xref:System.IntPtr?displayProperty=fullName>-Objekt ist, das einen Speicherort im Arbeitsspeicher darstellt, an dem sich der [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND)-Wert befindet. Das Festlegen der Eigenschaft auf form.Handle hatte unter Windows 7 und früheren Versionen keine Auswirkungen, unter Windows 8 und höheren Versionen resultiert dies jedoch in der Fehlermeldung &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot; (CryptographicException: Der Parameter ist falsch.).

#### <a name="suggestion"></a>Vorschlag

Für Apps mit der Zielplattform .NET Framework 4.7 oder höher, die eine übergeordnete Fensterbeziehung registrieren sollen, wird die Verwendung eines vereinfachten Formulars wie dem folgenden empfohlen:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

Einige Benutzer haben erkannt, dass der richtige zu übergebende Wert die Adresse eines Speicherorts im Arbeitsspeicher war, der den Wert `form.Handle` enthielt. Benutzer können sich gegen dieses geänderte Verhalten entscheiden, indem sie die AppContext-Option `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` auf `true` festlegen. Dies kann

- durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für AppContext, wie [hier](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46) beschrieben wird,
- Durch Hinzufügen der folgenden Zeile zum Abschnitt `<runtime>` der app.config-Datei:

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

Benutzer, die sich umgekehrt für das neue Verhalten der Laufzeit von .NET Framework 4.7 entscheiden, können die AppContext-Option auf `false` festlegen, wenn die Anwendung in älteren Versionen von .NET Framework geladen wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
