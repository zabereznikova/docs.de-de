---
title: HttpWebRequest._CoreResponse Feld
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155920"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="f05c6-102">HttpWebRequest. \_CoreResponse-Feld</span><span class="sxs-lookup"><span data-stu-id="f05c6-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="f05c6-103">`HttpWebRequest._CoreResponse`ist ein Objekt (entweder eine <xref:System.Exception> [CoreResponseData](coreresponsedata.md) oder ein ), die das Ergebnis der HTTP-Antwortanalyse enthält.</span><span class="sxs-lookup"><span data-stu-id="f05c6-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="f05c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f05c6-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="f05c6-105">Diese API ist nicht dazu gedacht, direkt in Ihrem Code verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="f05c6-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="f05c6-106">Stattdessen sollten Sie <xref:System.Diagnostics.DiagnosticSource> einen zum Hook-Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="f05c6-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="f05c6-107">Siehe [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="f05c6-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="f05c6-108">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="f05c6-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f05c6-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f05c6-109">Requirements</span></span>

<span data-ttu-id="f05c6-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f05c6-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f05c6-111">**Montage:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="f05c6-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f05c6-112">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="f05c6-112">**.NET Framework versions:** Available since 2.0.</span></span>
