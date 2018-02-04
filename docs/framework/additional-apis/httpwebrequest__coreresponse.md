---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="27ca0-102">HttpWebRequest-Anforderung. \_CoreResponse-Feld</span><span class="sxs-lookup"><span data-stu-id="27ca0-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="27ca0-103">`HttpWebRequest._CoreResponse`ein Objekt ist (entweder eine [CoreResponseData](coreresponsedata.md) oder ein <xref:System.Exception>), enthält das Ergebnis der Analyse von HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="27ca0-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="27ca0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27ca0-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="27ca0-105">Diese API ist nicht vorgesehen, direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27ca0-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="27ca0-106">Stattdessen sollten Sie verwenden eine <xref:System.Diagnostics.DiagnosticSource> Netzwerk-Code zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="27ca0-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="27ca0-107">Finden Sie unter [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="27ca0-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="27ca0-108">Microsoft unterstützt nicht die Verwendung dieser Klasse in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="27ca0-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="27ca0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27ca0-109">Requirements</span></span>

<span data-ttu-id="27ca0-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="27ca0-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="27ca0-111">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="27ca0-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="27ca0-112">**.NET Framework-Versionen:** verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="27ca0-112">**.NET Framework versions:** Available since 2.0.</span></span>
