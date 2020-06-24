---
title: Bekannte Typen in Datenverträgen
description: Erfahren Sie, wie das Daten Vertragsmodell die KnownTypeAttribute-Klasse verwendet, um die Typen anzugeben, die während der Deserialisierung in WCF eingeschlossen werden sollen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], known types
- KnownTypeAttribute [WCF]
- KnownTypes [WCF]
ms.assetid: 1a0baea1-27b7-470d-9136-5bbad86c4337
ms.openlocfilehash: 52b0caaaac976893dcf5ef5c228ccc4f53bdbe9e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247480"
---
# <a name="data-contract-known-types"></a><span data-ttu-id="e1274-103">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="e1274-103">Data Contract Known Types</span></span>
<span data-ttu-id="e1274-104">Die <xref:System.Runtime.Serialization.KnownTypeAttribute> -Klasse ermöglicht es Ihnen, vorab die Typen anzugeben, die während der Deserialisierung in Betracht gezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1274-104">The <xref:System.Runtime.Serialization.KnownTypeAttribute> class allows you to specify, in advance, the types that should be included for consideration during deserialization.</span></span> <span data-ttu-id="e1274-105">Ein Arbeitsbeispiel finden Sie unter [Known Types](../samples/known-types.md) .</span><span class="sxs-lookup"><span data-stu-id="e1274-105">For a working example, see the [Known Types](../samples/known-types.md) example.</span></span>  
  
 <span data-ttu-id="e1274-106">Beim Übergeben von Parametern und Rückgabewerten zwischen einem Client und einem Dienst verwenden normalerweise beide Endpunkte sämtliche Datenverträge für die zu übertragenden Daten gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="e1274-106">Normally, when passing parameters and return values between a client and a service, both endpoints share all of the data contracts of the data to be transmitted.</span></span> <span data-ttu-id="e1274-107">Unter den folgenden Umständen ist dies allerdings nicht der Fall:</span><span class="sxs-lookup"><span data-stu-id="e1274-107">However, this is not the case in the following circumstances:</span></span>  
  
- <span data-ttu-id="e1274-108">Der gesendete Datenvertrag wird vom erwarteten Datenvertrag abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e1274-108">The sent data contract is derived from the expected data contract.</span></span> <span data-ttu-id="e1274-109">Weitere Informationen finden Sie im Abschnitt zur Vererbung in der [Daten Vertrags Äquivalenz](data-contract-equivalence.md).</span><span class="sxs-lookup"><span data-stu-id="e1274-109">For more information, see the section about inheritance in [Data Contract Equivalence](data-contract-equivalence.md)).</span></span> <span data-ttu-id="e1274-110">In diesem Fall gilt für die übertragenen Daten nicht der Datenvertrag, der vom empfangenden Endpunkt erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-110">In that case, the transmitted data does not have the same data contract as expected by the receiving endpoint.</span></span>  
  
- <span data-ttu-id="e1274-111">Die zu übertragenden Informationen werden als zu einem Schnittstellentyp zugehörig deklariert, nicht als Klasse, Struktur oder Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e1274-111">The declared type for the information to be transmitted is an interface, as opposed to a class, structure, or enumeration.</span></span> <span data-ttu-id="e1274-112">Daher kann nicht im Vorhinein bekannt sein, welcher die Schnittstelle implementierende Typ tatsächlich gesendet wird, und folglich kann der empfangende Endpunkt nicht vorab den Datenvertrag für die übermittelten Daten bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e1274-112">Therefore, it cannot be known in advance which type that implements the interface is actually sent and therefore, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span>  
  
- <span data-ttu-id="e1274-113">Für die zu sendenden Informationen wird der Typ <xref:System.Object>deklariert.</span><span class="sxs-lookup"><span data-stu-id="e1274-113">The declared type for the information to be transmitted is <xref:System.Object>.</span></span> <span data-ttu-id="e1274-114">Weil jeder Typ von <xref:System.Object>erbt und nicht im Vorhinein bekannt sein kann, welcher die Schnittstelle implementierender Typ tatsächlich gesendet wird, und kann der empfangende Endpunkt nicht vorab den Datenvertrag für die übermittelten Daten bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e1274-114">Because every type inherits from <xref:System.Object>, and it cannot be known in advance which type is actually sent, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span> <span data-ttu-id="e1274-115">Dies ist ein Sonderfall des ersten Punkts: Jeder Datenvertrag ist vom Standardvertrag abgeleitet, d.&#160;h. einem leeren Vertrag, der für <xref:System.Object>generiert wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-115">This is a special case of the first item: Every data contract derives from the default, a blank data contract that is generated for <xref:System.Object>.</span></span>  
  
- <span data-ttu-id="e1274-116">Einige Typen, die .NET Framework Typen enthalten, haben Member, die sich in einer der drei vorangegangenen Kategorien befinden.</span><span class="sxs-lookup"><span data-stu-id="e1274-116">Some types, which include .NET Framework types, have members that are in one of the preceding three categories.</span></span> <span data-ttu-id="e1274-117">Zum Beispiel verwendet <xref:System.Collections.Hashtable> den Typ <xref:System.Object> , um die tatsächlichen Objekte in der Hashtabelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e1274-117">For example, <xref:System.Collections.Hashtable> uses <xref:System.Object> to store the actual objects in the hash table.</span></span> <span data-ttu-id="e1274-118">Beim Serialisieren dieser Typen kann die Empfängerseite nicht im Voraus den Datenvertrag für diese Member bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e1274-118">When serializing these types, the receiving side cannot determine in advance the data contract for these members.</span></span>  
  
## <a name="the-knowntypeattribute-class"></a><span data-ttu-id="e1274-119">Die KnownTypeAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="e1274-119">The KnownTypeAttribute Class</span></span>  
 <span data-ttu-id="e1274-120">Wenn Daten an einem empfangenden Endpunkt ankommen, versucht die WCF-Laufzeit, die Daten in eine Instanz eines Common Language Runtime (CLR)-Typs zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="e1274-120">When data arrives at a receiving endpoint, the WCF runtime attempts to deserialize the data into an instance of a common language runtime (CLR) type.</span></span> <span data-ttu-id="e1274-121">Zur Auswahl des Typs, der für die Deserialisierung instanziiert wird, wird zuerst die eingehende Nachricht überprüft, um den Datenvertrag zu ermitteln, dem der Inhalt der Nachricht entspricht.</span><span class="sxs-lookup"><span data-stu-id="e1274-121">The type that is instantiated for deserialization is chosen by first inspecting the incoming message to determine the data contract to which the contents of the message conform.</span></span> <span data-ttu-id="e1274-122">Die Deserialisierungs-Engine versucht dann, den CLR-Typ zu finden, der einen mit dem Nachrichteninhalt kompatiblen Datenvertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="e1274-122">The deserialization engine then attempts to find a CLR type that implements a data contract compatible with the message contents.</span></span> <span data-ttu-id="e1274-123">Die Gruppe potenzieller Typen, die die Deserialisierungs-Engine während dieses Prozesses zulässt, wird als die Gruppe "bekannter Typen" des Deserialisierers bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e1274-123">The set of candidate types that the deserialization engine allows for during this process is referred to as the deserializer's set of "known types."</span></span>  
  
 <span data-ttu-id="e1274-124">Eine Methode, die Deserialisierungs-Engine über einen Typ zu informieren, besteht im Einsatz von <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e1274-124">One way to let the deserialization engine know about a type is by using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="e1274-125">Das Attribut kann nicht auf einzelne Datenmember, sondern nur auf gesamte Datenvertragstypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-125">The attribute cannot be applied to individual data members, only to whole data contract types.</span></span> <span data-ttu-id="e1274-126">Das Attribut wird auf einen *äußeren Typ* angewendet, der eine Klasse oder eine Struktur sein kann.</span><span class="sxs-lookup"><span data-stu-id="e1274-126">The attribute is applied to an *outer type* that can be a class or a structure.</span></span> <span data-ttu-id="e1274-127">Grundsätzlich wird durch die Anwendung des Attributs ein Typ als "bekannter Typ" angegeben.</span><span class="sxs-lookup"><span data-stu-id="e1274-127">In its most basic usage, applying the attribute specifies a type as a "known type."</span></span> <span data-ttu-id="e1274-128">Dadurch wird der bekannte Typ Bestandteil der Gruppe bekannter Typen, wenn ein Objekt des äußeren Typs oder ein Objekt, auf das durch ein Member des äußeren Typs verwiesen wird, deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-128">This causes the known type to be a part of the set of known types whenever an object of the outer type or any object referred to through its members is being deserialized.</span></span> <span data-ttu-id="e1274-129">Auf einen Typ können mehrere <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-129">More than one <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute can be applied to the same type.</span></span>  
  
## <a name="known-types-and-primitives"></a><span data-ttu-id="e1274-130">Bekannte Typen und Primitive</span><span class="sxs-lookup"><span data-stu-id="e1274-130">Known Types and Primitives</span></span>  
 <span data-ttu-id="e1274-131">Primitive Typen sowie bestimmte Typen, die als primitiv behandelt werden (z.&#160;B. <xref:System.DateTime> und <xref:System.Xml.XmlElement>) sind immer "bekannt" und müssen nie mithilfe dieses Mechanismus hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-131">Primitive types, as well as certain types treated as primitives (for example, <xref:System.DateTime> and <xref:System.Xml.XmlElement>) are always "known" and never have to be added through this mechanism.</span></span> <span data-ttu-id="e1274-132">Arrays von primitiven Typen müssen allerdings explizit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-132">However, arrays of primitive types have to be added explicitly.</span></span> <span data-ttu-id="e1274-133">Die meisten Auflistungen werden als äquivalent mit Arrays betrachtet.</span><span class="sxs-lookup"><span data-stu-id="e1274-133">Most collections are considered equivalent to arrays.</span></span> <span data-ttu-id="e1274-134">(Nicht generische Auflistungen werden als äquivalent mit Arrays von <xref:System.Object>betrachtet).</span><span class="sxs-lookup"><span data-stu-id="e1274-134">(Non-generic collections are considered equivalent to arrays of <xref:System.Object>).</span></span> <span data-ttu-id="e1274-135">Ein Beispiel für die Verwendung von Primitiven, primitiven Arrays und primitiven Auflistungen finden Sie in Beispiel&#160;4.</span><span class="sxs-lookup"><span data-stu-id="e1274-135">For an example of the using primitives, primitive arrays, and primitive collections, see Example 4.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1274-136">Im Gegensatz zu anderen primitiven Typen ist die <xref:System.DateTimeOffset> -Struktur standardmäßig kein bekannter Typ. Daher muss sie der Liste bekannter Typen manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-136">Unlike other primitive types, the <xref:System.DateTimeOffset> structure is not a known type by default, so it must be manually added to the list of known types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e1274-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e1274-137">Examples</span></span>  
 <span data-ttu-id="e1274-138">In den folgenden Beispielen wird die Verwendung der <xref:System.Runtime.Serialization.KnownTypeAttribute> -Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e1274-138">The following examples show the <xref:System.Runtime.Serialization.KnownTypeAttribute> class in use.</span></span>  
  
#### <a name="example-1"></a><span data-ttu-id="e1274-139">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="e1274-139">Example 1</span></span>  
 <span data-ttu-id="e1274-140">Es sind drei Klassen mit einer Vererbungsbeziehung gegeben.</span><span class="sxs-lookup"><span data-stu-id="e1274-140">There are three classes with an inheritance relationship.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#1)]
 [!code-vb[C_KnownTypeAttribute#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#1)]  
  
 <span data-ttu-id="e1274-141">Die folgende `CompanyLogo` -Klasse kann serialisiert werden. Sie kann jedoch nicht deserialisiert werden, wenn der `ShapeOfLogo` -Member auf ein `CircleType` -Objekt oder ein `TriangleType` -Objekt festgelegt wird, weil die Deserialisierungs-Engine keine Typen mit Datenverträgen namens "Circle" oder "Triangle" erkennt.</span><span class="sxs-lookup"><span data-stu-id="e1274-141">The following `CompanyLogo` class can be serialized, but cannot be deserialized if the `ShapeOfLogo` member is set to either a `CircleType` or a `TriangleType` object, because the deserialization engine does not recognize any types with data contract names "Circle" or "Triangle."</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#2)]
 [!code-vb[C_KnownTypeAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#2)]  
  
 <span data-ttu-id="e1274-142">Im folgenden Code wird gezeigt, wie der `CompanyLogo` -Typ richtig geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-142">The correct way to write the `CompanyLogo` type is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#3)]
 [!code-vb[C_KnownTypeAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#3)]  
  
 <span data-ttu-id="e1274-143">Jedes Mal, wenn der äußere Typ `CompanyLogo2` deserialisiert wird, wird die Deserialisierungs-Engine über `CircleType` und `TriangleType` informiert und kann daher die passenden Typen für die Datenverträge namens "Circle" und "Triangle" finden.</span><span class="sxs-lookup"><span data-stu-id="e1274-143">Whenever the outer type `CompanyLogo2` is being deserialized, the deserialization engine knows about `CircleType` and `TriangleType` and, therefore, is able to find matching types for the "Circle" and "Triangle" data contracts.</span></span>  
  
#### <a name="example-2"></a><span data-ttu-id="e1274-144">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="e1274-144">Example 2</span></span>  
 <span data-ttu-id="e1274-145">Im folgenden Beispiel ist sowohl `CustomerTypeA` als auch `CustomerTypeB` der Datenvertrag `Customer` zugeordnet. Trotz dieser Tatsache wird jedes Mal eine Instanz von `CustomerTypeB` erstellt, wenn ein `PurchaseOrder` -Objekt deserialisiert wird, weil die Deserialisierungs-Engine nur `CustomerTypeB` kennt.</span><span class="sxs-lookup"><span data-stu-id="e1274-145">In the following example, even though both `CustomerTypeA` and `CustomerTypeB` have the `Customer` data contract, an instance of `CustomerTypeB` is created whenever a `PurchaseOrder` is deserialized, because only `CustomerTypeB` is known to the deserialization engine.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#4)]
 [!code-vb[C_KnownTypeAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#4)]  
  
#### <a name="example-3"></a><span data-ttu-id="e1274-146">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="e1274-146">Example 3</span></span>  
 <span data-ttu-id="e1274-147">Im folgenden Beispiel speichert ein <xref:System.Collections.Hashtable> seinen Inhalt intern als <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="e1274-147">In the following example, a <xref:System.Collections.Hashtable> stores its contents internally as <xref:System.Object>.</span></span> <span data-ttu-id="e1274-148">Um eine Hashtabelle erfolgreich deserialisieren zu können, muss die Deserialisierungs-Engine die Gruppe möglicher Typen kennen, die hier vorkommen können.</span><span class="sxs-lookup"><span data-stu-id="e1274-148">To successfully deserialize a hash table, the deserialization engine must know the set of possible types that can occur there.</span></span> <span data-ttu-id="e1274-149">In diesem Fall wissen wir im Vorhinein, dass nur `Book` -Objekte und `Magazine` -Objekte im `Catalog`gespeichert werden. Daher werden sie mithilfe des <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attributs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1274-149">In this case, we know in advance that only `Book` and `Magazine` objects are stored in the `Catalog`, so those are added using the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#5)]
 [!code-vb[C_KnownTypeAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#5)]  
  
#### <a name="example-4"></a><span data-ttu-id="e1274-150">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="e1274-150">Example 4</span></span>  
 <span data-ttu-id="e1274-151">Im folgenden Beispiel wird eine Zahl und ein Vorgang, der mit der Zahl ausgeführt werden soll, in einem Datenvertrag gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e1274-151">In the following example, a data contract stores a number and an operation to perform on the number.</span></span> <span data-ttu-id="e1274-152">Der `Numbers` -Datenmember kann eine ganze Zahl, ein Array von ganzen Zahlen oder ein Objekt des Typs <xref:System.Collections.Generic.List%601> sein, das ganze Zahlen enthält.</span><span class="sxs-lookup"><span data-stu-id="e1274-152">The `Numbers` data member can be an integer, an array of integers, or a <xref:System.Collections.Generic.List%601> that contains integers.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e1274-153">Dies funktioniert nur auf Clientseite, wenn zum Generieren eines WCF-Proxys SVCUTIL.EXE verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-153">This will only work on the client side if SVCUTIL.EXE is used to generate a WCF proxy.</span></span> <span data-ttu-id="e1274-154">SVCUTIL.EXE ruft Metadaten vom Dienst ab, einschließlich aller bekannter Typen.</span><span class="sxs-lookup"><span data-stu-id="e1274-154">SVCUTIL.EXE retrieves metadata from the service including any known types.</span></span> <span data-ttu-id="e1274-155">Ohne diese Informationen kann ein Client die Typen nicht deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="e1274-155">Without this information a client will not be able to deserialize the types.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#6)]
 [!code-vb[C_KnownTypeAttribute#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#6)]  
  
 <span data-ttu-id="e1274-156">Dies ist der Anwendungscode.</span><span class="sxs-lookup"><span data-stu-id="e1274-156">This is the application code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#7)]
 [!code-vb[C_KnownTypeAttribute#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#7)]  
  
## <a name="known-types-inheritance-and-interfaces"></a><span data-ttu-id="e1274-157">Bekannte Typen, Vererbung und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e1274-157">Known Types, Inheritance, and Interfaces</span></span>  
 <span data-ttu-id="e1274-158">Wenn ein bekannter Typ mithilfe des `KnownTypeAttribute` -Attributs mit einem bestimmten Typ verknüpft wird, wird der bekannte Typ auch mit allen von diesem Typ abgeleiteten Typen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e1274-158">When a known type is associated with a particular type using the `KnownTypeAttribute` attribute, the known type is also associated with all of the derived types of that type.</span></span> <span data-ttu-id="e1274-159">Beachten Sie beispielsweise folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="e1274-159">For example, see the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#8)]
 [!code-vb[C_KnownTypeAttribute#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#8)]  
  
 <span data-ttu-id="e1274-160">Die `DoubleDrawing` -Klasse erfordert nicht, dass das `KnownTypeAttribute` -Attribut mit `Square` und `Circle` im `AdditionalShape` -Feld verwendet wird, weil diese Attribute bereits auf die Basisklasse (`Drawing`) angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e1274-160">The `DoubleDrawing` class does not require the `KnownTypeAttribute` attribute to use `Square` and `Circle` in the `AdditionalShape` field, because the base class (`Drawing`) already has these attributes applied.</span></span>  
  
 <span data-ttu-id="e1274-161">Bekannte Typen können nur Klassen und Strukturen, nicht jedoch Schnittstellen, zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-161">Known types can be associated only with classes and structures, not interfaces.</span></span>  
  
## <a name="known-types-using-open-generic-methods"></a><span data-ttu-id="e1274-162">Bekannte Typen, die offene generische Methoden verwenden</span><span class="sxs-lookup"><span data-stu-id="e1274-162">Known Types Using Open Generic Methods</span></span>  
 <span data-ttu-id="e1274-163">Es ist möglicherweise notwendig, einen generischen Typ als bekannten Typ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1274-163">It may be necessary to add a generic type as a known type.</span></span> <span data-ttu-id="e1274-164">Ein offener generischer Typ kann dem `KnownTypeAttribute` -Attribut nicht als Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-164">However, an open generic type cannot be passed as a parameter to the `KnownTypeAttribute` attribute.</span></span>  
  
 <span data-ttu-id="e1274-165">Dieses Problem lässt sich mithilfe eines alternativen Mechanismus lösen: Schreiben Sie eine Methode, die eine Liste derjenigen Typen zurückgibt, welche der Auflistung bekannter Typen hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="e1274-165">This problem can be solved by using an alternative mechanism: Write a method that returns a list of types to add to the known types collection.</span></span> <span data-ttu-id="e1274-166">Wegen einigen Beschränkungen wird der Name der Methode dann als Zeichenfolgenargument für das `KnownTypeAttribute` -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="e1274-166">The name of the method is then specified as a string argument to the `KnownTypeAttribute` attribute due to some restrictions.</span></span>  
  
 <span data-ttu-id="e1274-167">Diese Methode muss für den Typ vorhanden sein, auf den das `KnownTypeAttribute` -Attribut angewendet wird. Sie muss statisch sein, darf keine Parameter annehmen und muss ein Objekt zurückgeben, das der <xref:System.Collections.IEnumerable> -Schnittstelle von <xref:System.Type>zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1274-167">The method must exist on the type to which the `KnownTypeAttribute` attribute is applied, must be static, must accept no parameters, and must return an object that can be assigned to <xref:System.Collections.IEnumerable> of <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="e1274-168">Es ist nicht möglich, das `KnownTypeAttribute` -Attribut mit einem Methodennamen und `KnownTypeAttribute` -Attribute mit tatsächlichen Typen für den gleichen Typ zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e1274-168">You cannot combine the `KnownTypeAttribute` attribute with a method name and `KnownTypeAttribute` attributes with actual types on the same type.</span></span> <span data-ttu-id="e1274-169">Weiterhin ist es nicht möglich, mehr als ein `KnownTypeAttribute` -Attribut mit einem Methodennamen auf den gleichen Typ anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="e1274-169">Furthermore, you cannot apply more than one `KnownTypeAttribute` with a method name to the same type.</span></span>  
  
 <span data-ttu-id="e1274-170">Siehe folgende Klasse.</span><span class="sxs-lookup"><span data-stu-id="e1274-170">See the following class.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#9)]
 [!code-vb[C_KnownTypeAttribute#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#9)]  
  
 <span data-ttu-id="e1274-171">Das `theDrawing` -Feld enthält Instanzen der generischen Klasse `ColorDrawing` und der generischen Klasse `BlackAndWhiteDrawing`, die beide von der generischen Klasse `Drawing`abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="e1274-171">The `theDrawing` field contains instances of a generic class `ColorDrawing` and a generic class `BlackAndWhiteDrawing`, both of which inherit from a generic class `Drawing`.</span></span> <span data-ttu-id="e1274-172">Normalerweise müssen beide Klassen den bekannten Typen hinzugefügt werden, aber der folgende Code stellt keine für Attribute gültige Syntax dar.</span><span class="sxs-lookup"><span data-stu-id="e1274-172">Normally, both must be added to known types, but the following is not valid syntax for attributes.</span></span>  
  
```csharp  
// Invalid syntax for attributes:  
// [KnownType(typeof(ColorDrawing<T>))]  
// [KnownType(typeof(BlackAndWhiteDrawing<T>))]  
```  
  
```vb  
' Invalid syntax for attributes:  
' <KnownType(GetType(ColorDrawing(Of T))), _  
' KnownType(GetType(BlackAndWhiteDrawing(Of T)))>  
```  
  
 <span data-ttu-id="e1274-173">Daher muss eine Methode erstellt werden, die diese Typen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e1274-173">Thus, a method must be created to return these types.</span></span> <span data-ttu-id="e1274-174">Im folgenden Code wird gezeigt, wie dieser Typ richtig geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-174">The correct way to write this type, then, is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#10)]
 [!code-vb[C_KnownTypeAttribute#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#10)]  
  
## <a name="additional-ways-to-add-known-types"></a><span data-ttu-id="e1274-175">Weitere Verfahren zum Hinzufügen bekannter Typen</span><span class="sxs-lookup"><span data-stu-id="e1274-175">Additional Ways to Add Known Types</span></span>  
 <span data-ttu-id="e1274-176">Darüber hinaus können bekannte Typen durch eine Konfigurationsdatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e1274-176">Additionally, known types can be added through a configuration file.</span></span> <span data-ttu-id="e1274-177">Dies ist hilfreich, wenn Sie nicht den Typ steuern, der bekannte Typen für die ordnungsgemäße Deserialisierung erfordert, z. b. bei der Verwendung von Typbibliotheken von Drittanbietern mit Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e1274-177">This is useful when you do not control the type that requires known types for proper deserialization, such as when using third-party type libraries with Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="e1274-178">Die folgende Konfigurationsdatei zeigt, wie in einer Konfigurationsdatei ein bekannter Typ angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e1274-178">The following configuration file shows how to specify a known type in a configuration file.</span></span>  
  
 `<configuration>`  
  
 `<system.runtime.serialization>`  
  
 `<dataContractSerializer>`  
  
 `<declaredTypes>`  
  
 `<add type="MyCompany.Library.Shape,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL">`  
  
 `<knownType type="MyCompany.Library.Circle,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL"/>`  
  
 `</add>`  
  
 `</declaredTypes>`  
  
 `</dataContractSerializer>`  
  
 `</system.runtime.serialization>`  
  
 `</configuration>`  
  
 <span data-ttu-id="e1274-179">In der vorangegangenen Konfigurationsdatei wird ein Datenvertragstyp mit der Bezeichnung `MyCompany.Library.Shape` deklariert, um `MyCompany.Library.Circle` als bekannten Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1274-179">In the preceding configuration file a data contract type called `MyCompany.Library.Shape` is declared to have `MyCompany.Library.Circle` as a known type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1274-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1274-180">See also</span></span>

- <xref:System.Runtime.Serialization.KnownTypeAttribute>
- <xref:System.Collections.Hashtable>
- <xref:System.Object>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>
- [<span data-ttu-id="e1274-181">Bekannte Typen</span><span class="sxs-lookup"><span data-stu-id="e1274-181">Known Types</span></span>](../samples/known-types.md)
- [<span data-ttu-id="e1274-182">Datenvertragsäquivalenz</span><span class="sxs-lookup"><span data-stu-id="e1274-182">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="e1274-183">Entwerfen von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="e1274-183">Designing Service Contracts</span></span>](../designing-service-contracts.md)
