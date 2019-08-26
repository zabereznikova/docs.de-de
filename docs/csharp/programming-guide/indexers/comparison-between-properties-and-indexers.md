---
title: Vergleich zwischen Eigenschaften und Indexern – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 4a14c2bf80ff203c5db7fc7663afeb816dc4a2c0
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589470"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="56497-102">Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="56497-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="56497-103">Indexer sind wie Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="56497-103">Indexers are like properties.</span></span> <span data-ttu-id="56497-104">Mit Ausnahme der in der folgenden Tabelle aufgeführten Unterschiede gelten alle für Eigenschaftenaccessoren definierten Regeln auch für Indexeraccessoren.</span><span class="sxs-lookup"><span data-stu-id="56497-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="56497-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="56497-105">Property</span></span>|<span data-ttu-id="56497-106">Indexer</span><span class="sxs-lookup"><span data-stu-id="56497-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="56497-107">Damit können Methoden wie allgemein zugängliche Datenmember aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="56497-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="56497-108">Damit können Elemente einer internen Auflistung eines Objekts durch die Anwendung der Arraynotation auf das Objekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="56497-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="56497-109">Der Zugriff erfolgt über einen einfachen Namen.</span><span class="sxs-lookup"><span data-stu-id="56497-109">Accessed through a simple name.</span></span>|<span data-ttu-id="56497-110">Der Zugriff erfolgt über einen Index.</span><span class="sxs-lookup"><span data-stu-id="56497-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="56497-111">Kann ein statischer Member oder ein Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="56497-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="56497-112">Muss ein Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="56497-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="56497-113">Ein [get](../../language-reference/keywords/get.md)-Accessor einer Eigenschaft weist keine Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="56497-113">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="56497-114">Ein `get`-Accessor eines Indexers hat dieselbe Liste formaler Parameter wie der Indexer.</span><span class="sxs-lookup"><span data-stu-id="56497-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="56497-115">Ein [set](../../language-reference/keywords/set.md)-Accessor einer Eigenschaft enthält den impliziten `value`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="56497-115">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="56497-116">Ein `set`-Accessor eines Indexers enthält neben dem [value](../../language-reference/keywords/value.md)-Parameter auch dieselbe Liste formaler Parameter wie der Indexer.</span><span class="sxs-lookup"><span data-stu-id="56497-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="56497-117">Unterstützt Kurzsyntax mit [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="56497-117">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="56497-118">Unterstützt Ausdruckskörpermember für nur abrufende Indexer.</span><span class="sxs-lookup"><span data-stu-id="56497-118">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56497-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56497-119">See also</span></span>

- [<span data-ttu-id="56497-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="56497-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="56497-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="56497-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="56497-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="56497-122">Properties</span></span>](../classes-and-structs/properties.md)
