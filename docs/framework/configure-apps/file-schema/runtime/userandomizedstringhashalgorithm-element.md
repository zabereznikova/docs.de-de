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
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153776"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="b6618-102">\<UseRandomizedStringHashAlgorithm>-Element</span><span class="sxs-lookup"><span data-stu-id="b6618-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="b6618-103">Bestimmt, ob die Common Language Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.</span><span class="sxs-lookup"><span data-stu-id="b6618-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a><span data-ttu-id="b6618-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6618-104">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6618-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6618-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b6618-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6618-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6618-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6618-107">Attributes</span></span>  
  
|<span data-ttu-id="b6618-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b6618-108">Attribute</span></span>|<span data-ttu-id="b6618-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b6618-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b6618-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b6618-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b6618-111">Gibt an, ob Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="b6618-111">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b6618-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="b6618-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="b6618-113">Wert</span><span class="sxs-lookup"><span data-stu-id="b6618-113">Value</span></span>|<span data-ttu-id="b6618-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b6618-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="b6618-115">Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen nicht pro Anwendungsdomäne; es wird ein einzelner Algorithmus verwendet, um Hashcodes für Zeichenfolgen zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b6618-115">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="b6618-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b6618-116">This is the default.</span></span>|  
|`1`|<span data-ttu-id="b6618-117">Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen pro Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b6618-117">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="b6618-118">Identische Zeichenfolgen in unterschiedlichen Anwendungsdomänen und in verschiedenen Prozessen weisen unterschiedliche Hashcodes auf.</span><span class="sxs-lookup"><span data-stu-id="b6618-118">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6618-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6618-119">Child Elements</span></span>  
 <span data-ttu-id="b6618-120">Keine</span><span class="sxs-lookup"><span data-stu-id="b6618-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6618-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6618-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b6618-122">Element</span><span class="sxs-lookup"><span data-stu-id="b6618-122">Element</span></span>|<span data-ttu-id="b6618-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6618-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b6618-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b6618-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b6618-125">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="b6618-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6618-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b6618-126">Remarks</span></span>  
 <span data-ttu-id="b6618-127">Standardmäßig verwenden die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode einen einzelnen Hashalgorithmus, der einen über verschiedene Anwendungsdomänen hinweg konsistenten Hashcode erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b6618-127">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="b6618-128">Dies entspricht dem Festlegen des `enabled`-Attributs des `<UseRandomizedStringHashAlgorithm>`-Elements auf `0`.</span><span class="sxs-lookup"><span data-stu-id="b6618-128">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="b6618-129">Dies ist der Hash Algorithmus, der in der .NET Framework 4 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6618-129">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="b6618-130">Die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode können auch einen anderen Hashalgorithmus verwenden, der Hashcodes pro Anwendungsdomäne berechnet.</span><span class="sxs-lookup"><span data-stu-id="b6618-130">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="b6618-131">Dadurch variieren Hashcodes für identische Zeichenfolgen von Anwendungsdomäne zu Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b6618-131">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="b6618-132">Dies ist eine Opt-In-Funktion; um sie zu nutzen, müssen Sie das `enabled`-Attribut des `<UseRandomizedStringHashAlgorithm>`-Elements auf `1` festlegen.</span><span class="sxs-lookup"><span data-stu-id="b6618-132">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="b6618-133">Die Zeichenfolgensuche in einer Hashtabelle ist in der Regel eine O(1)-Operation.</span><span class="sxs-lookup"><span data-stu-id="b6618-133">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="b6618-134">Wenn jedoch eine große Anzahl von Kollisionen auftritt, kann die Suche ein O (n<sup>2</sup>)-Vorgang werden.</span><span class="sxs-lookup"><span data-stu-id="b6618-134">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="b6618-135">Sie können das `<UseRandomizedStringHashAlgorithm>`-Konfigurationselement verwenden, um einen zufälligen Hashalgorithmus pro Anwendungsdomäne zu generieren. Dadurch wird die Anzahl der potenziellen Konflikte beschränkt, insbesondere wenn die Schlüssel, aus denen die Hashcodes berechnet werden, auf Dateneingaben durch Benutzer basieren.</span><span class="sxs-lookup"><span data-stu-id="b6618-135">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6618-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6618-136">Example</span></span>  
 <span data-ttu-id="b6618-137">Im folgenden Beispiel wird eine `DisplayString`-Klasse definiert, die die private Zeichenfolgenkonstante `s` enthält, deren Wert "Dies ist eine Zeichenfolge" lautet.</span><span class="sxs-lookup"><span data-stu-id="b6618-137">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="b6618-138">Außerdem enthält sie eine `ShowStringHashCode`-Methode, die den Zeichenfolgenwert und dessen Hashcode zusammen mit dem Namen der Anwendungsdomäne anzeigt, in der die Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b6618-138">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="b6618-139">Wenn Sie das Beispiel ausführen, ohne eine Konfigurationsdatei anzugeben, wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6618-139">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="b6618-140">Beachten Sie, dass die Hashcodes für die Zeichenfolge in den zwei Anwendungsdomänen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="b6618-140">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="b6618-141">Wenn Sie jedoch die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann das Beispiel ausführen, unterscheiden sich die Hashcodes je nach Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b6618-141">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b6618-142">Wenn die Konfigurationsdatei vorhanden ist, zeigt das Beispiel die folgende Ausgabe an:</span><span class="sxs-lookup"><span data-stu-id="b6618-142">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6618-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6618-143">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
