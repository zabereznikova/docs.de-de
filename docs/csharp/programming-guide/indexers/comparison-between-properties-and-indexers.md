---
title: Vergleich zwischen Eigenschaften und Indexern – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 330d222083ce599719698c023803196dfe88da84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712129"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a><span data-ttu-id="3452b-102">Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3452b-102">Comparison Between Properties and Indexers (C# Programming Guide)</span></span>
<span data-ttu-id="3452b-103">Indexer sind wie Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3452b-103">Indexers are like properties.</span></span> <span data-ttu-id="3452b-104">Mit Ausnahme der in der folgenden Tabelle aufgeführten Unterschiede gelten alle für Eigenschaftenaccessoren definierten Regeln auch für Indexeraccessoren.</span><span class="sxs-lookup"><span data-stu-id="3452b-104">Except for the differences shown in the following table, all the rules that are defined for property accessors apply to indexer accessors also.</span></span>  
  
|<span data-ttu-id="3452b-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3452b-105">Property</span></span>|<span data-ttu-id="3452b-106">Indexer</span><span class="sxs-lookup"><span data-stu-id="3452b-106">Indexer</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="3452b-107">Damit können Methoden wie allgemein zugängliche Datenmember aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3452b-107">Allows methods to be called as if they were public data members.</span></span>|<span data-ttu-id="3452b-108">Damit können Elemente einer internen Auflistung eines Objekts durch die Anwendung der Arraynotation auf das Objekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3452b-108">Allows elements of an internal collection of an object to be accessed by using array notation on the object itself.</span></span>|  
|<span data-ttu-id="3452b-109">Der Zugriff erfolgt über einen einfachen Namen.</span><span class="sxs-lookup"><span data-stu-id="3452b-109">Accessed through a simple name.</span></span>|<span data-ttu-id="3452b-110">Der Zugriff erfolgt über einen Index.</span><span class="sxs-lookup"><span data-stu-id="3452b-110">Accessed through an index.</span></span>|  
|<span data-ttu-id="3452b-111">Kann ein statischer Member oder ein Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="3452b-111">Can be a static or an instance member.</span></span>|<span data-ttu-id="3452b-112">Muss ein Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="3452b-112">Must be an instance member.</span></span>|  
|<span data-ttu-id="3452b-113">Ein [get](../../language-reference/keywords/get.md)-Accessor einer Eigenschaft weist keine Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="3452b-113">A [get](../../language-reference/keywords/get.md) accessor of a property has no parameters.</span></span>|<span data-ttu-id="3452b-114">Ein `get`-Accessor eines Indexers hat dieselbe Liste formaler Parameter wie der Indexer.</span><span class="sxs-lookup"><span data-stu-id="3452b-114">A `get` accessor of an indexer has the same formal parameter list as the indexer.</span></span>|  
|<span data-ttu-id="3452b-115">Ein [set](../../language-reference/keywords/set.md)-Accessor einer Eigenschaft enthält den impliziten `value`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="3452b-115">A [set](../../language-reference/keywords/set.md) accessor of a property contains the implicit `value` parameter.</span></span>|<span data-ttu-id="3452b-116">Ein `set`-Accessor eines Indexers enthält neben dem [value](../../language-reference/keywords/value.md)-Parameter auch dieselbe Liste formaler Parameter wie der Indexer.</span><span class="sxs-lookup"><span data-stu-id="3452b-116">A `set` accessor of an indexer has the same formal parameter list as the indexer, and also to the [value](../../language-reference/keywords/value.md) parameter.</span></span>|  
|<span data-ttu-id="3452b-117">Unterstützt Kurzsyntax mit [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3452b-117">Supports shortened syntax with [Auto-Implemented Properties](../classes-and-structs/auto-implemented-properties.md).</span></span>|<span data-ttu-id="3452b-118">Unterstützt Ausdruckskörpermember für nur abrufende Indexer.</span><span class="sxs-lookup"><span data-stu-id="3452b-118">Supports expression bodied members for get only indexers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3452b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3452b-119">See also</span></span>

- [<span data-ttu-id="3452b-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3452b-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3452b-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="3452b-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="3452b-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3452b-122">Properties</span></span>](../classes-and-structs/properties.md)
