---
title: S_isDebuggerCheckDisabledForTestPurposes-Feld
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ada3abcccac4244819cfbef1101a770761df6a50
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221920"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="568ed-102">S_isDebuggerCheckDisabledForTestPurposes-Feld</span><span class="sxs-lookup"><span data-stu-id="568ed-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="568ed-103">Dieses private Feld in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse wird von Visual Studio verwendet, um festzustellen, ob eine interne Überprüfung auf einen aktiven Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="568ed-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="568ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="568ed-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="568ed-105">APIs in der `System.Windows.Diagnostics.VisualDiagnostics` Klasse sind nur verfügbar, wenn eine Anwendung unter einem Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="568ed-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="568ed-106">Legen Sie `s_isDebuggerCheckDisabledForTestPurposes` zu `true` den Zugriff auf die APIs außerhalb eines Debuggers.</span><span class="sxs-lookup"><span data-stu-id="568ed-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="568ed-107">Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="568ed-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="568ed-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="568ed-108">Requirements</span></span>

<span data-ttu-id="568ed-109">**Namespace:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="568ed-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="568ed-110">**Assembly:** PresentationCore (in "PresentationCore.dll")</span><span class="sxs-lookup"><span data-stu-id="568ed-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="568ed-111">**.NET Framework-Versionen:** Verfügbar seit 4.6.</span><span class="sxs-lookup"><span data-stu-id="568ed-111">**.NET Framework versions:** Available since 4.6.</span></span>