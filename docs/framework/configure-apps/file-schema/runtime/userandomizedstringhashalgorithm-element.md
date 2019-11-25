---
title: <UseRandomizedStringHashAlgorithm>-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: 3863bc1376d89ef804022fb9c87fac3a25fc910f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968844"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="f210f-102">\<userandomizedstringhashalgorithm > Element</span><span class="sxs-lookup"><span data-stu-id="f210f-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="f210f-103">Bestimmt, ob die Common Language Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.</span><span class="sxs-lookup"><span data-stu-id="f210f-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="f210f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f210f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f210f-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="f210f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f210f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<userandomizedstringhashalgorithm >**</span><span class="sxs-lookup"><span data-stu-id="f210f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f210f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f210f-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f210f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f210f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f210f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f210f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f210f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f210f-110">Attributes</span></span>  
  
|<span data-ttu-id="f210f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f210f-111">Attribute</span></span>|<span data-ttu-id="f210f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f210f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f210f-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="f210f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f210f-114">Gibt an, ob Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="f210f-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f210f-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="f210f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f210f-116">Wert</span><span class="sxs-lookup"><span data-stu-id="f210f-116">Value</span></span>|<span data-ttu-id="f210f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f210f-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="f210f-118">Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen nicht pro Anwendungsdomäne; es wird ein einzelner Algorithmus verwendet, um Hashcodes für Zeichenfolgen zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="f210f-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="f210f-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="f210f-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="f210f-120">Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen pro Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f210f-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="f210f-121">Identische Zeichenfolgen in unterschiedlichen Anwendungsdomänen und in verschiedenen Prozessen weisen unterschiedliche Hashcodes auf.</span><span class="sxs-lookup"><span data-stu-id="f210f-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f210f-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f210f-122">Child Elements</span></span>  
 <span data-ttu-id="f210f-123">Keine</span><span class="sxs-lookup"><span data-stu-id="f210f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f210f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f210f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f210f-125">Element</span><span class="sxs-lookup"><span data-stu-id="f210f-125">Element</span></span>|<span data-ttu-id="f210f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f210f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f210f-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f210f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f210f-128">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="f210f-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f210f-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f210f-129">Remarks</span></span>  
 <span data-ttu-id="f210f-130">Standardmäßig verwenden die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode einen einzelnen Hashalgorithmus, der einen über verschiedene Anwendungsdomänen hinweg konsistenten Hashcode erzeugt.</span><span class="sxs-lookup"><span data-stu-id="f210f-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="f210f-131">Dies entspricht dem Festlegen des `enabled`-Attributs des `<UseRandomizedStringHashAlgorithm>`-Elements auf `0`.</span><span class="sxs-lookup"><span data-stu-id="f210f-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="f210f-132">Dies ist der Hash Algorithmus, der in der .NET Framework 4 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f210f-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="f210f-133">Die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode können auch einen anderen Hashalgorithmus verwenden, der Hashcodes pro Anwendungsdomäne berechnet.</span><span class="sxs-lookup"><span data-stu-id="f210f-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="f210f-134">Dadurch variieren Hashcodes für identische Zeichenfolgen von Anwendungsdomäne zu Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f210f-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="f210f-135">Dies ist eine Opt-In-Funktion; um sie zu nutzen, müssen Sie das `enabled`-Attribut des `<UseRandomizedStringHashAlgorithm>`-Elements auf `1` festlegen.</span><span class="sxs-lookup"><span data-stu-id="f210f-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="f210f-136">Die Zeichenfolgensuche in einer Hashtabelle ist in der Regel eine O(1)-Operation.</span><span class="sxs-lookup"><span data-stu-id="f210f-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="f210f-137">Wenn jedoch eine große Anzahl von Kollisionen auftritt, kann die Suche ein O (n<sup>2</sup>)-Vorgang werden.</span><span class="sxs-lookup"><span data-stu-id="f210f-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="f210f-138">Sie können das `<UseRandomizedStringHashAlgorithm>`-Konfigurationselement verwenden, um einen zufälligen Hashalgorithmus pro Anwendungsdomäne zu generieren. Dadurch wird die Anzahl der potenziellen Konflikte beschränkt, insbesondere wenn die Schlüssel, aus denen die Hashcodes berechnet werden, auf Dateneingaben durch Benutzer basieren.</span><span class="sxs-lookup"><span data-stu-id="f210f-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f210f-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f210f-139">Example</span></span>  
 <span data-ttu-id="f210f-140">Im folgenden Beispiel wird eine `DisplayString`-Klasse definiert, die die private Zeichenfolgenkonstante `s` enthält, deren Wert "Dies ist eine Zeichenfolge" lautet.</span><span class="sxs-lookup"><span data-stu-id="f210f-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="f210f-141">Außerdem enthält sie eine `ShowStringHashCode`-Methode, die den Zeichenfolgenwert und dessen Hashcode zusammen mit dem Namen der Anwendungsdomäne anzeigt, in der die Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f210f-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="f210f-142">Wenn Sie das Beispiel ausführen, ohne eine Konfigurationsdatei anzugeben, wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f210f-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="f210f-143">Beachten Sie, dass die Hashcodes für die Zeichenfolge in den zwei Anwendungsdomänen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f210f-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="f210f-144">Wenn Sie jedoch die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann das Beispiel ausführen, unterscheiden sich die Hashcodes je nach Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f210f-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="f210f-145">Wenn die Konfigurationsdatei vorhanden ist, zeigt das Beispiel die folgende Ausgabe an:</span><span class="sxs-lookup"><span data-stu-id="f210f-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="f210f-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f210f-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
