---
title: '@ (C#-Referenz)'
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08e3da6aaeee037d7272ea8cddc4382a436b683b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-c-reference"></a><span data-ttu-id="b9f25-102">@ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b9f25-102">@ (C# Reference)</span></span>

<span data-ttu-id="b9f25-103">Das Sonderzeichen `@` dient als ausführlicher Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="b9f25-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="b9f25-104">Er wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="b9f25-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="b9f25-105">Zum Aktivieren von C#-Schlüsselwörtern, die als Bezeichner verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9f25-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="b9f25-106">Das Zeichen `@` steht vor einem Codeelement, das der Compiler als Bezeichner und nicht als C#-Schlüsselwort interpretieren soll.</span><span class="sxs-lookup"><span data-stu-id="b9f25-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="b9f25-107">Im folgenden Beispiel wird das Zeichen `@` zum Definieren eines Bezeichners mit dem Namen `for` verwendet, der in einer `for`-Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9f25-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   <span data-ttu-id="b9f25-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="b9f25-108">[!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]</span></span>

1. <span data-ttu-id="b9f25-109">Zum Angeben, dass ein Zeichenfolgenliteral wörtlich interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9f25-109">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="b9f25-110">Das Zeichen `@` in dieser Instanz definiert ein *ausführliches Zeichenfolgenliteral*.</span><span class="sxs-lookup"><span data-stu-id="b9f25-110">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="b9f25-111">Einfache Escapesequenzen (z.B. `"\\"` für einen umgekehrten Schrägstrich), Escapesequenzen für Hexadezimalzahlen (z.B. `"\x0041"` für ein groß geschriebenes A) und Escapesequenzen für Unicodezeichen (wie z.B. `"\u0041"` für ein groß geschriebenes A) werden wörtlich interpretiert.</span><span class="sxs-lookup"><span data-stu-id="b9f25-111">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A, and Unicode escape sequences, such as `"\u0041"` for an uppercase A, are interpreted literally.</span></span> <span data-ttu-id="b9f25-112">Nur eine Escapesequenz für Anführungszeichen (`""`) wird nicht wörtlich interpretiert; es wird ein einfaches Anführungszeichen generiert.</span><span class="sxs-lookup"><span data-stu-id="b9f25-112">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="b9f25-113">Im folgenden Beispiel werden zwei identische Dateipfade definiert – einer durch Verwendung eines regulären Zeichenfolgenliterals und der andere durch ein ausführliches Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="b9f25-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="b9f25-114">Dies ist einer der häufigeren Verwendungsarten von ausführlichen Zeichenfolgenliteralen.</span><span class="sxs-lookup"><span data-stu-id="b9f25-114">This is one of the more common uses of verbatim string literals.</span></span>

   <span data-ttu-id="b9f25-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="b9f25-115">[!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]</span></span>

   <span data-ttu-id="b9f25-116">Im folgenden Beispiel werden die Auswirkungen des Definierens eines regulären Zeichenfolgenliterals und eines ausführlichen Zeichenfolgenliterals mit identischen Zeichensequenzen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9f25-116">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   <span data-ttu-id="b9f25-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="b9f25-117">[!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]</span></span>

1. <span data-ttu-id="b9f25-118">Zum Zulassen, dass der Compiler im Fall eines Namenskonflikts zwischen Attributen unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="b9f25-118">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="b9f25-119">Ein Attribut ist ein von @System.Attribute abgeleiteter Typ.</span><span class="sxs-lookup"><span data-stu-id="b9f25-119">An attribute is a type that derives from @System.Attribute.</span></span> <span data-ttu-id="b9f25-120">Der Name des Typs enthält normalerweise das Suffix **Attribute**, obwohl der Compiler diese Konvention nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="b9f25-120">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="b9f25-121">Auf das Attribut kann dann im Code entweder über den vollständigen Typnamen (z.B. `[InfoAttribute]`) oder über den gekürzten Namen (z.B. `[Info]`) verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b9f25-121">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="b9f25-122">Allerdings tritt ein Namenskonflikt auf, wenn zwei gekürzte Typnamen des Attributs identisch sind und ein Typname das Suffix **Attribute** enthält, der andere jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="b9f25-122">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="b9f25-123">Der folgende Code kann z.B. nicht kompiliert werden, da der Compiler nicht bestimmen kann, ob das Attribut `Info` oder `InfoAttribute` auf die Methode `Main` angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9f25-123">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Main` method.</span></span>

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   <span data-ttu-id="b9f25-124">Wenn der ausführliche Bezeichner zum Identifizieren des Attributs `Info` verwendet wird, kann das Beispiel erfolgreich kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b9f25-124">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   <span data-ttu-id="b9f25-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="b9f25-125">[!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b9f25-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9f25-126">See Also</span></span>  
 <span data-ttu-id="b9f25-127">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b9f25-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b9f25-128">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b9f25-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b9f25-129">C# Special Characters (C#-Sonderzeichen)</span><span class="sxs-lookup"><span data-stu-id="b9f25-129">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)

