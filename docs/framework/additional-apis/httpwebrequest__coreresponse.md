---
title: HttpWebRequest._CoreResponse-Feld
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
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706064"
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="913ea-102">"HttpWebRequest". \_CoreResponse-Feld</span><span class="sxs-lookup"><span data-stu-id="913ea-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="913ea-103">`HttpWebRequest._CoreResponse` ist ein Objekt (entweder eine [CoreResponseData](coreresponsedata.md) oder <xref:System.Exception>), die das Ergebnis der Analyse von HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="913ea-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="913ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="913ea-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="913ea-105">Diese API ist nicht vorgesehen, direkt in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="913ea-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="913ea-106">Sie sollten stattdessen eine <xref:System.Diagnostics.DiagnosticSource> Netzwerk-Code zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="913ea-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="913ea-107">Finden Sie unter [DiagnosticSource-Benutzerhandbuch](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="913ea-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="913ea-108">Microsoft unterstützt nicht die Verwendung dieser Klasse in einer produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="913ea-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="913ea-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="913ea-109">Requirements</span></span>

<span data-ttu-id="913ea-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="913ea-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="913ea-111">**Assembly:** System (in "System.dll")</span><span class="sxs-lookup"><span data-stu-id="913ea-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="913ea-112">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="913ea-112">**.NET Framework versions:** Available since 2.0.</span></span>
