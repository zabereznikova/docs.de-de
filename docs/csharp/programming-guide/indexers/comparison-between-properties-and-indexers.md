---
title: Vergleich zwischen Eigenschaften und Indexern – C#-Programmierhandbuch
description: Vergleichen Sie Indexer in C# mit Eigenschaften. Abgesehen von einigen Unterschieden gelten die für Eigenschaftenaccessoren definierten Regeln auch für Indexeraccessoren.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: b83ce3db3d4b53fb7bcc5f3b3cd603a375d5d473
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299174"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="26eed-104">Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="26eed-104">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="26eed-105">Indexer sind wie Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="26eed-105">Indexers are like properties.</span></span> <span data-ttu-id="26eed-106">Mit Ausnahme der in der folgenden Tabelle aufgeführten Unterschiede gelten alle für Eigenschaftenaccessoren definierten Regeln auch für Indexeraccessoren.</span><span class="sxs-lookup"><span data-stu-id="26eed-106">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="26eed-107">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="26eed-107">Property</span></span>|<span data-ttu-id="26eed-108">Indexer</span><span class="sxs-lookup"><span data-stu-id="26eed-108">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="26eed-109">Damit können Methoden wie allgemein zugängliche Datenmember aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="26eed-109">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="26eed-110">Damit können Elemente einer internen Auflistung eines Objekts durch die Anwendung der Arraynotation auf das Objekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="26eed-110">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="26eed-111">Der Zugriff erfolgt über einen einfachen Namen.</span><span class="sxs-lookup"><span data-stu-id="26eed-111">Accessed through a simple name.</span></span>|<span data-ttu-id="26eed-112">Der Zugriff erfolgt über einen Index.</span><span class="sxs-lookup"><span data-stu-id="26eed-112">Accessed through an index.</span></span>|  
|<span data-ttu-id="26eed-113">Kann ein statischer Member oder ein Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="26eed-113">Can be a static or an instance member.</span></span>|<span data-ttu-id="26eed-114">Muss ein Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="26eed-114">Must be an instance member.</span></span>|  
|<span data-ttu-id="26eed-115">Ein [get](../../language-reference/keywords/get.md)-Accessor einer Eigenschaft weist keine Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="26eed-115">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="26eed-116">Ein `get`-Accessor eines Indexers hat dieselbe Liste formaler Parameter wie der Indexer.</span><span class="sxs-lookup"><span data-stu-id="26eed-116">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="26eed-117">Ein [set](../../language-reference/keywords/set.md)-Accessor einer Eigenschaft enthält den impliziten `value`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="26eed-117">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="26eed-118">Ein `set`-Accessor eines Indexers enthält neben dem [value](../../language-reference/keywords/value.md)-Parameter auch dieselbe Liste formaler Parameter wie der Indexer.</span><span class="sxs-lookup"><span data-stu-id="26eed-118">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="26eed-119">Unterstützt Kurzsyntax mit [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="26eed-119">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="26eed-120">Unterstützt Ausdruckskörpermember für nur abrufende Indexer.</span><span class="sxs-lookup"><span data-stu-id="26eed-120">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26eed-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26eed-121">See also</span></span>

- [<span data-ttu-id="26eed-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="26eed-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="26eed-123">Indexer</span><span class="sxs-lookup"><span data-stu-id="26eed-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="26eed-124">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="26eed-124">Properties</span></span>](../classes-and-structs/properties.md)
