---
title: Feld "HttpWebRequest. _CoreResponse"
description: Informieren Sie sich über das Feld "HttpWebRequest. _CoreResponse" in .net. Dieses Feld ist ein coreresponsedata-oder Exception-Objekt, das das Ergebnis der Analyse der HTTP-Antwort enthält.
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
ms.openlocfilehash: 5093ec7ed2c3b94931dcd622ae9ccdb42feffa18
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989757"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="75f53-104">HttpWebRequest. \_ Coreresponse-Feld</span><span class="sxs-lookup"><span data-stu-id="75f53-104">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="75f53-105">`HttpWebRequest._CoreResponse`ist ein Objekt ( [coreresponsedata](coreresponsedata.md) oder <xref:System.Exception> ), das das Ergebnis der HTTP-Antwort Analyse enthält.</span><span class="sxs-lookup"><span data-stu-id="75f53-105">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="75f53-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="75f53-106">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="75f53-107">Diese API ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="75f53-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="75f53-108">Stattdessen sollten Sie einen <xref:System.Diagnostics.DiagnosticSource> zum Anschließen von Netzwerkcode verwenden.</span><span class="sxs-lookup"><span data-stu-id="75f53-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="75f53-109">Weitere Informationen finden Sie [im Benutzerhandbuch für diagnosticsource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="75f53-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="75f53-110">Microsoft unterstützt die Verwendung dieser Klasse in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="75f53-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="75f53-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="75f53-111">Requirements</span></span>

<span data-ttu-id="75f53-112">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="75f53-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="75f53-113">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="75f53-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="75f53-114">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="75f53-114">**.NET Framework versions:** Available since 2.0.</span></span>
