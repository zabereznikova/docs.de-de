---
title: S_isDebuggerCheckDisabledForTestPurposes Feld
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name: System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location: PresentationCore.dll
api_type: Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.openlocfilehash: 97e5d32bff3e3150b56e8d9492aacc40f09f2afe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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

**Namespace:**<xref:System.Windows.Diagnostics>

**Assembly:** PresentationCore (in PresentationCore.dll)

**.NET Framework-Versionen:** verfügbar seit 4.6.
