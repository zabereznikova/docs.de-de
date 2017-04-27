---
title: "Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: 22c258b06a5cc8fa3fec72665d7e413b0cdd11ee
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a>Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND

Die <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>-Eigenschaft, die in .NET Framework 2.0 eingeführt wurde, ermöglicht einer Anwendung die Registrierung eines Handlewerts für das übergeordnete Fenster, sodass jedes Benutzeroberflächenelement, das auf den Schlüssel zugreifen muss (wie etwa eine PIN-Eingabeaufforderung oder ein Zustimmungsdialogfeld), als untergeordnetes modales Fenster des angegebenen Fensters geöffnet wird. Von Anwendungen mit der Zielplattform .NET Framework 4.7 an kann dieser Eigenschaft ein Fensterhandle (HWND) zugewiesen werden.

In Versionen von .NET Framework bis einschließlich .NET Framework 4.6.2 wurde als zugewiesener Wert der <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>-Eigenschaft ein <xref:System.IntPtr> erwartet, der den Speicherort im Arbeitsspeicher angibt, an dem sich der HWND-Wert befindet. In Windows 7 und früheren Versionen des Windows-Betriebssystems blieb das Festlegen der Eigenschaft auf `form.Handle` ohne Auswirkung, in Windows 8 und späteren Versionen führt es jedoch zu einem <xref:System.Security.Cryptography> mit der Nachricht „Der Parameter ist falsch“.

Von Apps für die Zielplattform .NET Framework 4.7 an kann eine Windows Forms-Anwendung die <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>-Eigenschaft mit Code wie dem folgenden festlegen:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a>Auswirkungen

Für Anwendungen für die Zielplattform .NET Framework 4.7 oder höher, die eine übergeordnete Fensterbeziehung registrieren möchten, wird vorzugsweise die vereinfachte Form verwendet:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a>Problemumgehung

Entwickler, die bestimmt hatten, dass der richtige Wert die Adresse des Speicherorts im Arbeitsspeicher war, der den `form.Handle`-Wert enthielt, können sich gegen dieses geänderte Verhalten entscheiden, indem sie den Schalter <xref:System.Security.AppContext> `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` auf `true` festlegen:

- Durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für die [AppContext](assetID:///T:System.Security.AppContext)-Instanz.

- Durch Hinzufügen der folgenden Zeile zum Abschnitt `<runtime>` der app.config-Datei:
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

Benutzer, die sich umgekehrt für das neue Verhalten entscheiden, können für Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, jedoch frühere Versionen von .NET Framework als Zielplattform haben, den <xref:System.Security.AppContext>-Schalter auf `false` festlegen.
 
## <a name="see-also"></a>Siehe auch

[Änderungen der Neuzuweisungen in .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

