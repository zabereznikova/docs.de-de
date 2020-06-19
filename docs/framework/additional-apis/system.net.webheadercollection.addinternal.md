---
title: WebHeaderCollection. addinternal-Methode (System.net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990446"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="a8632-102">WebHeaderCollection. addinternal-Methode</span><span class="sxs-lookup"><span data-stu-id="a8632-102">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="a8632-103">Fügt der Auflistung einen neuen Header mit dem angegebenen Namen und Wert hinzu, wobei die Überprüfungen umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="a8632-103">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="a8632-104">Diese Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8632-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a8632-105">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="a8632-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="a8632-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8632-106">Parameters</span></span>

- <span data-ttu-id="a8632-107">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a8632-107">`name` <xref:System.String></span></span>

  <span data-ttu-id="a8632-108">Der Name des Headers.</span><span class="sxs-lookup"><span data-stu-id="a8632-108">The name of the header.</span></span>

- <span data-ttu-id="a8632-109">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a8632-109">`value` <xref:System.String></span></span>

  <span data-ttu-id="a8632-110">Der Wert des Headers.</span><span class="sxs-lookup"><span data-stu-id="a8632-110">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8632-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a8632-111">Requirements</span></span>

<span data-ttu-id="a8632-112">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a8632-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a8632-113">**Assembly:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="a8632-113">**Assembly:** System (in System.dll)</span></span>
