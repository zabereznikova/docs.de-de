---
title: Schritte im Serialisierungsprozess
description: Der Serialisierungsprozess beginnt, wenn die Serialize-Methode für einen Formatierer aufgerufen wird. In diesem Artikel wird die Abfolge der Ereignisse beschrieben.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: 1f749b9102182e78bc3fda436cf386a9f5759d5a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379100"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="1c8e9-104">Schritte im Serialisierungsprozess</span><span class="sxs-lookup"><span data-stu-id="1c8e9-104">Steps in the serialization process</span></span>
<span data-ttu-id="1c8e9-105">Wenn die <xref:System.Runtime.Serialization.Formatter.Serialize%2A>-Methode für ein [Formatierungsprogramm](xref:System.Runtime.Serialization.Formatter) aufgerufen wird, erfolgt die Objektserialisierung nach den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="1c8e9-105">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="1c8e9-106">Es wird überprüft, ob das Formatierungsprogramm über einen Ersatzselektor verfügt.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-106">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="1c8e9-107">Ist dies beim vorliegenden Formatierungsprogramm der Fall, wird geprüft, ob der Ersatzselektor Objekte des gegebenen Typs handhaben kann.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-107">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="1c8e9-108">Wenn der Selektor den Objekttyp handhaben kann, wird <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> im Ersatzselektor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-108">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="1c8e9-109">Wenn kein Ersatzselektor vorhanden ist oder wenn der gegebene Ersatzselektor den Objekttyp nicht handhaben kann, wird geprüft, ob das Objekt mit dem [Serialisierbar](xref:System.SerializableAttribute)-Attribut markiert ist.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-109">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="1c8e9-110">Wenn dies nicht der Fall ist, wird <xref:System.Runtime.Serialization.SerializationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-110">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="1c8e9-111">Wenn das Objekt entsprechend markiert ist, wird geprüft, ob das Objekt die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-111">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="1c8e9-112">Falls dem so ist, wird die <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> des Objekts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-112">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="1c8e9-113">Wenn das Objekt <xref:System.Runtime.Serialization.ISerializable> nicht implementiert, wird nach der Standardserialisierungsrichtlinie verfahren, und alle Felder, die nicht als [Nicht serialisierbar](xref:System.NonSerializedAttribute) markiert sind, werden serialisiert.</span><span class="sxs-lookup"><span data-stu-id="1c8e9-113">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="1c8e9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c8e9-114">See also</span></span>

- [<span data-ttu-id="1c8e9-115">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1c8e9-115">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="1c8e9-116">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1c8e9-116">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
