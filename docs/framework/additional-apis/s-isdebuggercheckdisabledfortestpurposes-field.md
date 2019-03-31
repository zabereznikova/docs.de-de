---
title: S_isDebuggerCheckDisabledForTestPurposes-Feld
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ab71ab6aa2b0ed454b86388ba369204a2131cca5
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634426"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>S_isDebuggerCheckDisabledForTestPurposes-Feld

Dieses private Feld in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse wird von Visual Studio verwendet, um festzustellen, ob eine interne Überprüfung auf einen aktiven Debugger ausgeführt wird.

## <a name="syntax"></a>Syntax

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> -APIs in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse sind nur verfügbar, wenn eine Anwendung unter einem Debugger ausgeführt wird. Legen Sie `s_isDebuggerCheckDisabledForTestPurposes` zu `true` den Zugriff auf die APIs außerhalb eines Debuggers.
>
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Windows.Diagnostics>

**Assembly:** PresentationCore (in "PresentationCore.dll")

**.NET Framework-Versionen:** Verfügbar seit 4.6.