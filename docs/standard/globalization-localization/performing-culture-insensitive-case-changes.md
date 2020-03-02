---
title: Durchführen kulturunabhängiger Schreibungsänderungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
ms.openlocfilehash: 7b2dee03619e24c5a2845699a06e88abab0c594b
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160130"
---
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="97d6e-102">Durchführen kulturunabhängiger Schreibungsänderungen</span><span class="sxs-lookup"><span data-stu-id="97d6e-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="97d6e-103">Die Methoden <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> und <xref:System.Char.ToLower%2A?displayProperty=nameWithType> stellen Überladungen bereit, die keine Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="97d6e-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="97d6e-104">Standardmäßig führen diese Überladungen ohne Parameter die Schreibungsänderungen auf Basis des <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>-Werts durch.</span><span class="sxs-lookup"><span data-stu-id="97d6e-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="97d6e-105">Die unter Berücksichtigung der Groß-/Kleinschreibung erzielten Ergebnisse variieren je nach Kultur.</span><span class="sxs-lookup"><span data-stu-id="97d6e-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="97d6e-106">Um klar anzugeben, ob die Schreibungsänderungen kulturabhängig oder kulturunabhängig erfolgen sollen, empfiehlt sich die Verwendung der Überladungen dieser Methoden, für die explizit ein `culture`-Parameter festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="97d6e-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="97d6e-107">Um kulturabhängige Schreibungsänderungen zu aktivieren, geben Sie `CultureInfo.CurrentCulture` für den `culture`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="97d6e-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="97d6e-108">Um kulturunabhängige Schreibungsänderungen zu aktivieren, geben Sie `CultureInfo.InvariantCulture` für den `culture`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="97d6e-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="97d6e-109">Häufig werden Zeichenfolgen in eine Standardschreibweise konvertiert, um spätere Suchvorgänge zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="97d6e-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="97d6e-110">Wenn Zeichenfolgen auf diese Weise verwendet werden, sollte `CultureInfo.InvariantCulture` für den `culture`-Parameter angegeben werden, da sich der Wert von <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> zwischen dem Zeitpunkt der Schreibungsänderung und dem Zeitpunkt des Suchvorgangs ändern kann.</span><span class="sxs-lookup"><span data-stu-id="97d6e-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="97d6e-111">Wenn darüber hinaus eine Sicherheitsentscheidung auf einer Änderung von Groß- und Kleinschreibung beruht, sollte die Operation kulturunabhängig sein, um sicherzustellen, dass das Ergebnis nicht durch den Wert von `CultureInfo.CurrentCulture` beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="97d6e-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="97d6e-112">Im Abschnitt „Zeichenfolgenvergleiche mit der aktuellen Kultur“ im Artikel [Bewährte Methoden für die Verwendung von Zeichenfolgen in .NET](../../../docs/standard/base-types/best-practices-strings.md) finden Sie ein Beispiel, das veranschaulicht, wie kulturabhängige Zeichenfolgenoperationen zu inkonsistenten Ergebnissen führen können.</span><span class="sxs-lookup"><span data-stu-id="97d6e-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="97d6e-113">Verwenden der String.ToUpper-Methode und der String.ToLower-Methode</span><span class="sxs-lookup"><span data-stu-id="97d6e-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="97d6e-114">Aus Gründen der Übersichtlichkeit des Codes wird empfohlen, immer die Überladungen der `String.ToUpper`-Methode und der `String.ToLower`-Methode zu verwenden, bei denen ein `culture`-Parameter explizit angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="97d6e-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="97d6e-115">Mit dem folgenden Code wird z. B. nach einem Bezeichner gesucht.</span><span class="sxs-lookup"><span data-stu-id="97d6e-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="97d6e-116">In der Standardeinstellung ist die `key.ToLower`-Operation kulturabhängig, jedoch wird dieses Verhalten beim Lesen des Codes nicht deutlich.</span><span class="sxs-lookup"><span data-stu-id="97d6e-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="97d6e-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97d6e-117">Example</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 <span data-ttu-id="97d6e-118">Wenn Sie eine kulturunabhängige `key.ToLower`-Operation ausführen möchten, muss das vorige Beispiel so geändert werden, dass beim Ändern der Schreibweise `CultureInfo.InvariantCulture` explizit verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="97d6e-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="97d6e-119">Verwenden der Char.ToUpper-Methode und der Char.ToLower-Methode</span><span class="sxs-lookup"><span data-stu-id="97d6e-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="97d6e-120">Obwohl die `Char.ToUpper`-Methode und die `Char.ToLower`-Methode über die gleichen Eigenschaften wie die `String.ToUpper`-Methode und die `String.ToLower`-Methode verfügen, sind nur die Kulturen Türkisch (Türkei) und Aserbaidschanisch (lateinisch, Aserbaidschan) betroffen.</span><span class="sxs-lookup"><span data-stu-id="97d6e-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="97d6e-121">Hierbei handelt es sich um die beiden einzigen Kulturen mit Unterschieden in der Groß-/Kleinschreibung für ein einzelnes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="97d6e-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="97d6e-122">Weitere Informationen über diese Besonderheit bei der Groß-/Kleinschreibung finden Sie im Abschnitt "Groß-/Kleinschreibung" im Thema zur <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="97d6e-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="97d6e-123">Aus Gründen der Übersichtlichkeit des Codes empfiehlt es sich, immer die Überladungen dieser Methoden zu verwenden, bei denen ein `culture`-Parameter explizit festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="97d6e-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d6e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97d6e-124">See also</span></span>

- <xref:System.String.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.String.ToLower%2A?displayProperty=nameWithType>
- <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.Char.ToLower%2A?displayProperty=nameWithType>
- [<span data-ttu-id="97d6e-125">Durchführen kulturunabhängiger Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="97d6e-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
