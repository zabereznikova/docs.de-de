---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7cd561cf0e0a9e080b150bdaa412686126423c91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="6e39b-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span><span class="sxs-lookup"><span data-stu-id="6e39b-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="6e39b-103">Bestimmt, ob die Common Language Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.</span><span class="sxs-lookup"><span data-stu-id="6e39b-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="6e39b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6e39b-104">\<configuration></span></span>  
<span data-ttu-id="6e39b-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="6e39b-105">\<runtime></span></span>  
<span data-ttu-id="6e39b-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="6e39b-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e39b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e39b-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e39b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e39b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e39b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e39b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e39b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e39b-110">Attributes</span></span>  
  
|<span data-ttu-id="6e39b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6e39b-111">Attribute</span></span>|<span data-ttu-id="6e39b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e39b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6e39b-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6e39b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6e39b-114">Gibt an, ob Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="6e39b-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6e39b-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="6e39b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6e39b-116">Wert</span><span class="sxs-lookup"><span data-stu-id="6e39b-116">Value</span></span>|<span data-ttu-id="6e39b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e39b-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="6e39b-118">Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen nicht pro Anwendungsdomäne; es wird ein einzelner Algorithmus verwendet, um Hashcodes für Zeichenfolgen zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="6e39b-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="6e39b-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="6e39b-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="6e39b-120">Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen pro Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6e39b-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="6e39b-121">Identische Zeichenfolgen in unterschiedlichen Anwendungsdomänen und in verschiedenen Prozessen weisen unterschiedliche Hashcodes auf.</span><span class="sxs-lookup"><span data-stu-id="6e39b-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e39b-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e39b-122">Child Elements</span></span>  
 <span data-ttu-id="6e39b-123">Keine</span><span class="sxs-lookup"><span data-stu-id="6e39b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e39b-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e39b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6e39b-125">Element</span><span class="sxs-lookup"><span data-stu-id="6e39b-125">Element</span></span>|<span data-ttu-id="6e39b-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e39b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6e39b-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6e39b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6e39b-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="6e39b-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e39b-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e39b-129">Remarks</span></span>  
 <span data-ttu-id="6e39b-130">Standardmäßig verwenden die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode einen einzelnen Hashalgorithmus, der einen über verschiedene Anwendungsdomänen hinweg konsistenten Hashcode erzeugt.</span><span class="sxs-lookup"><span data-stu-id="6e39b-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="6e39b-131">Dies entspricht dem Festlegen des `enabled`-Attributs des `<UseRandomizedStringHashAlgorithm>`-Elements auf `0`.</span><span class="sxs-lookup"><span data-stu-id="6e39b-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="6e39b-132">Dies ist der Hashalgorithmus, der in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e39b-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="6e39b-133">Die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode können auch einen anderen Hashalgorithmus verwenden, der Hashcodes pro Anwendungsdomäne berechnet.</span><span class="sxs-lookup"><span data-stu-id="6e39b-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="6e39b-134">Dadurch variieren Hashcodes für identische Zeichenfolgen von Anwendungsdomäne zu Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6e39b-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="6e39b-135">Dies ist eine Opt-In-Funktion; um sie zu nutzen, müssen Sie das `enabled`-Attribut des `<UseRandomizedStringHashAlgorithm>`-Elements auf `1` festlegen.</span><span class="sxs-lookup"><span data-stu-id="6e39b-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="6e39b-136">Die Zeichenfolgensuche in einer Hashtabelle ist in der Regel eine O(1)-Operation.</span><span class="sxs-lookup"><span data-stu-id="6e39b-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="6e39b-137">Jedoch, wenn eine große Anzahl von Konflikten auftreten, die Suche kann auch eine o (n<sup>2</sup>) Vorgang.</span><span class="sxs-lookup"><span data-stu-id="6e39b-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="6e39b-138">Sie können das `<UseRandomizedStringHashAlgorithm>`-Konfigurationselement verwenden, um einen zufälligen Hashalgorithmus pro Anwendungsdomäne zu generieren. Dadurch wird die Anzahl der potenziellen Konflikte beschränkt, insbesondere wenn die Schlüssel, aus denen die Hashcodes berechnet werden, auf Dateneingaben durch Benutzer basieren.</span><span class="sxs-lookup"><span data-stu-id="6e39b-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e39b-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e39b-139">Example</span></span>  
 <span data-ttu-id="6e39b-140">Im folgenden Beispiel wird eine `DisplayString`-Klasse definiert, die die private Zeichenfolgenkonstante `s` enthält, deren Wert "Dies ist eine Zeichenfolge" lautet.</span><span class="sxs-lookup"><span data-stu-id="6e39b-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="6e39b-141">Außerdem enthält sie eine `ShowStringHashCode`-Methode, die den Zeichenfolgenwert und dessen Hashcode zusammen mit dem Namen der Anwendungsdomäne anzeigt, in der die Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e39b-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="6e39b-142">Wenn Sie das Beispiel ausführen, ohne eine Konfigurationsdatei anzugeben, wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e39b-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="6e39b-143">Beachten Sie, dass die Hashcodes für die Zeichenfolge in den zwei Anwendungsdomänen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="6e39b-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="6e39b-144">Wenn Sie jedoch die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann das Beispiel ausführen, unterscheiden sich die Hashcodes je nach Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6e39b-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6e39b-145">Wenn die Konfigurationsdatei vorhanden ist, zeigt das Beispiel die folgende Ausgabe an:</span><span class="sxs-lookup"><span data-stu-id="6e39b-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e39b-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e39b-146">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
