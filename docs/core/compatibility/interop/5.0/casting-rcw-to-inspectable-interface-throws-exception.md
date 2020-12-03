---
title: 'Breaking Change: Umwandeln eines RCW in `InterfaceIsIInspectable` löst eine Ausnahme aus'
description: Hier erfahren Sie mehr über den Interop-Breaking-Change in .NET 5.0, durch den das Umwandeln eines RCW in eine `InterfaceIsIInspectable`-Schnittstelle die Ausnahme „PlatformNotSupportedException“ auslöst.
ms.date: 09/13/2020
ms.openlocfilehash: 7c0f37057aebcc41d0c00d949b921ec3a4bdf012
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759480"
---
# <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a>Umwandlung des RCW in eine `InterfaceIsIInspectable`-Schnittstelle löst PlatformNotSupportedException aus

Wenn ein RCW (Runtime Callable Wrapper) in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle umgewandelt wird, wird jetzt <xref:System.PlatformNotSupportedException> ausgelöst. Diese Änderung folgt der [Entfernung der WinRT-Unterstützung aus .NET](built-in-support-for-winrt-removed.md).

## <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

## <a name="change-description"></a>Änderungsbeschreibung

In .NET-Versionen vor .NET 5.0 Preview 6 funktioniert das Umwandeln eines RCW in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle wie gewohnt. In .NET 5.0 Preview 6 bis Preview 8 und in .NET 5.0 RC1 können Sie einen RCW erfolgreich in eine <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Schnittstelle umwandeln. Möglicherweise gilt das Ausführen von Methoden für die Schnittstelle jedoch als Zugriffsverletzung, da die zugrunde liegende Unterstützung in [.NET 5.0 Preview 6](built-in-support-for-winrt-removed.md) aus der Runtime entfernt wurde.

In .NET 5.0 RC2 und höher löst das Umwandeln eines RCW in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle zur Umwandlungszeit <xref:System.PlatformNotSupportedException> aus.

## <a name="reason-for-change"></a>Grund für die Änderung

Die Unterstützung von <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> wurde in einer [früheren Vorschauversion von .NET 5.0](built-in-support-for-winrt-removed.md) entfernt. Das Umwandeln in eine <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Schnittstelle wurde dabei jedoch versehentlich nicht bedacht. Da die zugrunde liegende Unterstützung in der Runtime nicht mehr vorhanden ist, erzeugt das Auslösen von <xref:System.PlatformNotSupportedException> einen ordnungsgemäßen Fehlerpfad. Durch die ausgelöste Ausnahme ist zudem leichter erkennbar, dass das Feature nicht mehr unterstützt wird.

## <a name="recommended-action"></a>Empfohlene Maßnahme

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

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

### Category

Interop

-->
