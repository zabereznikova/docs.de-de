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
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="f1852-102">S_isDebuggerCheckDisabledForTestPurposes Feld</span><span class="sxs-lookup"><span data-stu-id="f1852-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="f1852-103">Diese privates Feld in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse wird von Visual Studio verwendet, um festzustellen, ob eine interne für einen aktiven Debugger gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1852-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1852-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1852-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="f1852-105">API in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse sind nur verfügbar, wenn eine Anwendung unter einem Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f1852-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="f1852-106">Legen Sie `s_isDebuggerCheckDisabledForTestPurposes` zu `true` , die einen Debugger-APIs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f1852-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="f1852-107">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="f1852-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="f1852-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1852-108">Requirements</span></span>

<span data-ttu-id="f1852-109">**Namespace:**<xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="f1852-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="f1852-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="f1852-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="f1852-111">**.NET Framework-Versionen:** verfügbar seit 4.6.</span><span class="sxs-lookup"><span data-stu-id="f1852-111">**.NET Framework versions:** Available since 4.6.</span></span>
