---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438049"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a>Umwandlung des RCW in eine `InterfaceIsIInspectable`-Schnittstelle löst PlatformNotSupportedException aus

Wenn ein RCW (Runtime Callable Wrapper) in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle umgewandelt wird, wird jetzt <xref:System.PlatformNotSupportedException> ausgelöst. Diese Änderung folgt der [Entfernung der WinRT-Unterstützung aus .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET-Versionen vor .NET 5.0 Preview 6 funktioniert das Umwandeln eines RCW in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle wie gewohnt. In .NET 5.0 Preview 6 bis Preview 8 und in .NET 5.0 RC1 können Sie einen RCW erfolgreich in eine <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Schnittstelle umwandeln. Möglicherweise gilt das Ausführen von Methoden für die Schnittstelle jedoch als Zugriffsverletzung, da die zugrunde liegende Unterstützung in [.NET 5.0 Preview 6](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net) aus der Runtime entfernt wurde.

In .NET 5.0 RC2 und höher löst das Umwandeln eines RCW in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle zur Umwandlungszeit <xref:System.PlatformNotSupportedException> aus.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Unterstützung von <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> wurde in einer [früheren Vorschauversion von .NET 5.0](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net) entfernt. Das Umwandeln in eine <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Schnittstelle wurde dabei jedoch versehentlich nicht bedacht. Da die zugrunde liegende Unterstützung in der Runtime nicht mehr vorhanden ist, erzeugt das Auslösen von <xref:System.PlatformNotSupportedException> einen ordnungsgemäßen Fehlerpfad. Durch die ausgelöste Ausnahme ist zudem leichter erkennbar, dass das Feature nicht mehr unterstützt wird.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

- Wenn Sie die Schnittstelle in der WinMD-Datei (Windows-Runtimemetadaten) definieren können, verwenden Sie das C#/WinRT-Tool.

- Kennzeichnen Sie die Schnittstelle andernfalls als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> anstelle von <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, und fügen Sie am Anfang der Schnittstelle drei Platzhaltereinträge für die <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Methoden hinzu. Der folgende Codeausschnitt zeigt ein Beispiel.

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

#### <a name="category"></a>Kategorie

Interop

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->
