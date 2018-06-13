---
title: S_isDebuggerCheckDisabledForTestPurposes Feld
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
robots: noindex,nofollow
ms.openlocfilehash: fbbd8d33ea163efaad1417ab4a1435df729e4897
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752200"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>S_isDebuggerCheckDisabledForTestPurposes Feld

Diese privates Feld in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse wird von Visual Studio verwendet, um festzustellen, ob eine interne für einen aktiven Debugger gesucht werden soll.

## <a name="syntax"></a>Syntax
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse sind nur verfügbar, wenn eine Anwendung unter einem Debugger ausgeführt wird. Legen Sie `s_isDebuggerCheckDisabledForTestPurposes` zu `true` , die einen Debugger-APIs zugreifen.  
>   
>  Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.  

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Windows.Diagnostics>

**Assembly:** PresentationCore (in PresentationCore.dll)

**.NET Framework-Versionen:** verfügbar seit 4.6.
