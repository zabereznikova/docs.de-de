---
title: '@ (C#-Referenz)'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7dbab5a743b4f9fed759210e8410cd6e3459efac
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43750021"
---
# <a name="-c-reference"></a><span data-ttu-id="a24f8-102">@ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a24f8-102">@ (C# Reference)</span></span>

<span data-ttu-id="a24f8-103">Das Sonderzeichen `@` dient als ausführlicher Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="a24f8-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="a24f8-104">Er wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="a24f8-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="a24f8-105">Zum Aktivieren von C#-Schlüsselwörtern, die als Bezeichner verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a24f8-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="a24f8-106">Das Zeichen `@` steht vor einem Codeelement, das der Compiler als Bezeichner und nicht als C#-Schlüsselwort interpretieren soll.</span><span class="sxs-lookup"><span data-stu-id="a24f8-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="a24f8-107">Im folgenden Beispiel wird das Zeichen `@` zum Definieren eines Bezeichners mit dem Namen `for` verwendet, der in einer `for`-Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a24f8-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="a24f8-108">Zum Angeben, dass ein Zeichenfolgenliteral wörtlich interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a24f8-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="a24f8-109">Das Zeichen `@` in dieser Instanz definiert ein *ausführliches Zeichenfolgenliteral*.</span><span class="sxs-lookup"><span data-stu-id="a24f8-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="a24f8-110">Einfache Escapesequenzen (z.B. `"\\"` für einen umgekehrten Schrägstrich), Escapesequenzen für Hexadezimalzahlen (z.B. `"\x0041"` für ein groß geschriebenes A) und Escapesequenzen für Unicodezeichen (wie z.B. `"\u0041"` für ein groß geschriebenes A) werden wörtlich interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a24f8-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="a24f8-111">Nur eine Escapesequenz für Anführungszeichen (`""`) wird nicht wörtlich interpretiert; es wird ein einfaches Anführungszeichen generiert.</span><span class="sxs-lookup"><span data-stu-id="a24f8-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="a24f8-112">Bei einer ausführlichen [interpolierten Zeichenfolge](interpolated.md) werden darüber hinaus Klammern als Escapesequenzen (`{{` und `}}`) nicht wörtlich interpretiert. In diesem Fall werden einfache geschweifte Klammerzeichen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="a24f8-112">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="a24f8-113">Im folgenden Beispiel werden zwei identische Dateipfade definiert – einer durch Verwendung eines regulären Zeichenfolgenliterals und der andere durch ein ausführliches Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="a24f8-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="a24f8-114">Dies ist einer der häufigeren Verwendungsarten von ausführlichen Zeichenfolgenliteralen.</span><span class="sxs-lookup"><span data-stu-id="a24f8-114">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="a24f8-115">Im folgenden Beispiel werden die Auswirkungen des Definierens eines regulären Zeichenfolgenliterals und eines ausführlichen Zeichenfolgenliterals mit identischen Zeichensequenzen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a24f8-115">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="a24f8-116">Zum Zulassen, dass der Compiler im Fall eines Namenskonflikts zwischen Attributen unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="a24f8-116">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="a24f8-117">Ein Attribut ist ein von <xref:System.Attribute> abgeleiteter Typ.</span><span class="sxs-lookup"><span data-stu-id="a24f8-117">An attribute is a type that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="a24f8-118">Der Name des Typs enthält normalerweise das Suffix **Attribute**, obwohl der Compiler diese Konvention nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="a24f8-118">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="a24f8-119">Auf das Attribut kann dann im Code entweder über den vollständigen Typnamen (z.B. `[InfoAttribute]`) oder über den gekürzten Namen (z.B. `[Info]`) verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a24f8-119">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="a24f8-120">Allerdings tritt ein Namenskonflikt auf, wenn zwei gekürzte Typnamen des Attributs identisch sind und ein Typname das Suffix **Attribute** enthält, der andere jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="a24f8-120">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="a24f8-121">Der folgende Code kann z.B. nicht kompiliert werden, da der Compiler nicht bestimmen kann, ob das Attribut `Info` oder `InfoAttribute` auf die Klasse `Example` angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a24f8-121">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span>

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

   <span data-ttu-id="a24f8-122">Wenn der ausführliche Bezeichner zum Identifizieren des Attributs `Info` verwendet wird, kann das Beispiel erfolgreich kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a24f8-122">If the verbatim identifier is used to identify the `Info` attribute, the example compiles successfully.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a><span data-ttu-id="a24f8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a24f8-123">See Also</span></span>

- [<span data-ttu-id="a24f8-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a24f8-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a24f8-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a24f8-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a24f8-126">C#-Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="a24f8-126">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)
