---
title: Typkonvertierungstabellen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e741de47fec5f0ed607bba33b963d449c5c51cce
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="type-conversion-tables-in-net"></a><span data-ttu-id="c69cb-102">Typkonvertierungstabellen in .NET</span><span class="sxs-lookup"><span data-stu-id="c69cb-102">Type Conversion Tables in .NET</span></span>
<span data-ttu-id="c69cb-103">Eine erweiternde Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der gleich groß oder größer ist.</span><span class="sxs-lookup"><span data-stu-id="c69cb-103">Widening conversion occurs when a value of one type is converted to another type that is of equal or greater size.</span></span> <span data-ttu-id="c69cb-104">Eine einschränkende Konvertierung tritt auf, wenn ein Wert eines bestimmten Typs in einen anderen Typ konvertiert wird, der kleiner ist.</span><span class="sxs-lookup"><span data-stu-id="c69cb-104">A narrowing conversion occurs when a value of one type is converted to a value of another type that is of a smaller size.</span></span> <span data-ttu-id="c69cb-105">Die Tabellen in diesem Thema veranschaulichen die Verhaltensweisen dieser beiden Konvertierungsarten.</span><span class="sxs-lookup"><span data-stu-id="c69cb-105">The tables in this topic illustrate the behaviors exhibited by both types of conversions.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="c69cb-106">Erweiterungskonvertierungen</span><span class="sxs-lookup"><span data-stu-id="c69cb-106">Widening Conversions</span></span>  
 <span data-ttu-id="c69cb-107">Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die ohne Informationsverlust ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c69cb-107">The following table describes the widening conversions that can be performed without the loss of information.</span></span>  
  
|<span data-ttu-id="c69cb-108">Typ</span><span class="sxs-lookup"><span data-stu-id="c69cb-108">Type</span></span>|<span data-ttu-id="c69cb-109">Kann ohne Datenverlust konvertiert werden in</span><span class="sxs-lookup"><span data-stu-id="c69cb-109">Can be converted without data loss to</span></span>|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<span data-ttu-id="c69cb-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.SByte>|<span data-ttu-id="c69cb-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="c69cb-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="c69cb-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Char>|<span data-ttu-id="c69cb-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="c69cb-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="c69cb-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="c69cb-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 <span data-ttu-id="c69cb-117">Einige erweiternde Konvertierungen zu <xref:System.Single> oder <xref:System.Double> können zu einem Genauigkeitsverlust führen.</span><span class="sxs-lookup"><span data-stu-id="c69cb-117">Some widening conversions to <xref:System.Single> or <xref:System.Double> can cause a loss of precision.</span></span> <span data-ttu-id="c69cb-118">Die folgende Tabelle beschreibt die erweiternden Konvertierungen, die einen Informationsverlust nach sich ziehen können.</span><span class="sxs-lookup"><span data-stu-id="c69cb-118">The following table describes the widening conversions that sometimes result in a loss of information.</span></span>  
  
|<span data-ttu-id="c69cb-119">Typ</span><span class="sxs-lookup"><span data-stu-id="c69cb-119">Type</span></span>|<span data-ttu-id="c69cb-120">Kann konvertiert werden in</span><span class="sxs-lookup"><span data-stu-id="c69cb-120">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<span data-ttu-id="c69cb-121"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="c69cb-121"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="c69cb-122"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="c69cb-122"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="c69cb-123"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="c69cb-123"><xref:System.Single>, <xref:System.Double></span></span>|  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="c69cb-124">Eingrenzungskonvertierungen</span><span class="sxs-lookup"><span data-stu-id="c69cb-124">Narrowing Conversions</span></span>  
 <span data-ttu-id="c69cb-125">Eine einschränkende Konvertierung in <xref:System.Single> oder <xref:System.Double> kann zu einem Informationsverlust führen.</span><span class="sxs-lookup"><span data-stu-id="c69cb-125">A narrowing conversion to <xref:System.Single> or <xref:System.Double> can cause a loss of information.</span></span> <span data-ttu-id="c69cb-126">Wenn der Zieltyp die Quelle nicht mit der gleichen Detailgenauigkeit und im gleichen Umfang wiedergeben kann, wird der resultierende Typ auf die Konstante `PositiveInfinity` oder `NegativeInfinity` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c69cb-126">If the target type cannot properly express the magnitude of the source, the resulting type is set to the constant `PositiveInfinity` or `NegativeInfinity`.</span></span> <span data-ttu-id="c69cb-127">`PositiveInfinity` resultiert aus der Division einer positiven Zahl durch null und wird auch zurückgegeben, wenn der Wert eines <xref:System.Single>- oder <xref:System.Double>-Typs den Wert des Felds `MaxValue` überschreitet.</span><span class="sxs-lookup"><span data-stu-id="c69cb-127">`PositiveInfinity` results from dividing a positive number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> exceeds the value of the `MaxValue` field.</span></span> <span data-ttu-id="c69cb-128">`NegativeInfinity` resultiert aus der Division einer negativen Zahl durch null und wird auch zurückgegeben, wenn der Wert eines <xref:System.Single>- oder <xref:System.Double>-Typs den Wert des Felds `MinValue` unterschreitet.</span><span class="sxs-lookup"><span data-stu-id="c69cb-128">`NegativeInfinity` results from dividing a negative number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> falls below the value of the `MinValue` field.</span></span> <span data-ttu-id="c69cb-129">Eine Konvertierung aus einem <xref:System.Double>- in einen <xref:System.Single>-Typ kann zu `PositiveInfinity` oder `NegativeInfinity` führen.</span><span class="sxs-lookup"><span data-stu-id="c69cb-129">A conversion from a <xref:System.Double> to a <xref:System.Single> might result in `PositiveInfinity` or `NegativeInfinity`.</span></span>  
  
 <span data-ttu-id="c69cb-130">Eine einschränkende Konvertierung kann auch zum Verlust von Informationen für andere Datentypen führen.</span><span class="sxs-lookup"><span data-stu-id="c69cb-130">A narrowing conversion can also result in a loss of information for other data types.</span></span> <span data-ttu-id="c69cb-131">Es wird jedoch eine <xref:System.OverflowException> ausgelöst, wenn der Wert eines zu konvertierenden Typs außerhalb des von den Feldern `MaxValue` und `MinValue` des Zieltyps angegebenen Bereichs liegt und die Konvertierung von der Runtime geprüft wird, um sicherzustellen, dass der Wert des Zieltyps den `MaxValue` oder `MinValue` nicht überschreitet.</span><span class="sxs-lookup"><span data-stu-id="c69cb-131">However, an <xref:System.OverflowException> is thrown if the value of a type that is being converted falls outside of the range specified by the target type's `MaxValue` and `MinValue` fields, and the conversion is checked by the runtime to ensure that the value of the target type does not exceed its `MaxValue` or `MinValue`.</span></span> <span data-ttu-id="c69cb-132">Konvertierungen, die mit der <xref:System.Convert?displayProperty=nameWithType>-Klasse ausgeführt werden, werden immer auf diese Weise überprüft.</span><span class="sxs-lookup"><span data-stu-id="c69cb-132">Conversions that are performed with the <xref:System.Convert?displayProperty=nameWithType> class are always checked in this manner.</span></span>  
  
 <span data-ttu-id="c69cb-133">Die folgende Tabelle enthält Konvertierungen, die eine <xref:System.OverflowException> über <xref:System.Convert?displayProperty=nameWithType> oder eine andere Konvertierungsprüfung auslösen, wenn der Wert des zu konvertierenden Typs außerhalb des definierten Bereichs des resultierenden Typs liegt.</span><span class="sxs-lookup"><span data-stu-id="c69cb-133">The following table lists conversions that throw an <xref:System.OverflowException> using <xref:System.Convert?displayProperty=nameWithType> or any checked conversion if the value of the type being converted is outside the defined range of the resulting type.</span></span>  
  
|<span data-ttu-id="c69cb-134">Typ</span><span class="sxs-lookup"><span data-stu-id="c69cb-134">Type</span></span>|<span data-ttu-id="c69cb-135">Kann konvertiert werden in</span><span class="sxs-lookup"><span data-stu-id="c69cb-135">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<span data-ttu-id="c69cb-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="c69cb-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="c69cb-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="c69cb-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="c69cb-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="c69cb-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="c69cb-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="c69cb-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="c69cb-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="c69cb-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span></span>|  
|<xref:System.Int64>|<span data-ttu-id="c69cb-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="c69cb-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="c69cb-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="c69cb-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="c69cb-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="c69cb-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Single>|<span data-ttu-id="c69cb-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="c69cb-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Double>|<span data-ttu-id="c69cb-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="c69cb-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c69cb-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c69cb-146">See Also</span></span>  
 <xref:System.Convert?displayProperty=nameWithType>  
 [<span data-ttu-id="c69cb-147">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="c69cb-147">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
