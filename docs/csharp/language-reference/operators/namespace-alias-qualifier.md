---
title: 'Operator „::“: C#-Referenz'
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
- global
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: f91287ed281a2c6b10bed93cff10b08972a8445e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855126"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="56287-102">Operator „::“ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="56287-102">:: operator (C# reference)</span></span>

<span data-ttu-id="56287-103">Verwenden Sie den Namespacealias-Qualifizierer `::`, um auf einen Member eines Namespace mit Alias zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="56287-103">Use the namespace alias qualifier `::` to access a member of an aliased namespace.</span></span> <span data-ttu-id="56287-104">Sie können den `::`-Qualifizierer nur zwischen zwei Bezeichnern verwenden.</span><span class="sxs-lookup"><span data-stu-id="56287-104">You can use the `::` qualifier only between two identifiers.</span></span> <span data-ttu-id="56287-105">Der linke Bezeichner kann einer der folgenden Aliase sein:</span><span class="sxs-lookup"><span data-stu-id="56287-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="56287-106">Ein mit einer [using alias-Anweisung](../keywords/using-directive.md) erstellter Namespacealias:</span><span class="sxs-lookup"><span data-stu-id="56287-106">A namespace alias created with a [using alias directive](../keywords/using-directive.md):</span></span>

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="56287-107">Ein [externer Alias](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="56287-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="56287-108">Der `global`-Alias, ein globaler Namespacealias.</span><span class="sxs-lookup"><span data-stu-id="56287-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="56287-109">Der globale Namespace ist der Namespace, der Namespaces und Typen enthält, die nicht in einem benannten Namespace deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="56287-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="56287-110">Bei Verwendung mit dem `::`-Qualifizierer verweist der `global`-Alias immer auf den globalen Namespace, auch wenn ein benutzerdefinierter `global` Namespacealias vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="56287-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>

  <span data-ttu-id="56287-111">Im folgenden Beispiel wird der `global`-Alias verwendet, um auf den .NET-Namespace <xref:System> zuzugreifen, der ein Member des globalen Namespace ist.</span><span class="sxs-lookup"><span data-stu-id="56287-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="56287-112">Ohne den `global`-Alias würde auf den benutzerdefinierten `System`-Namespace, der ein Member des `MyCompany.MyProduct`-Namespace ist, zugegriffen:</span><span class="sxs-lookup"><span data-stu-id="56287-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }

      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```

  > [!NOTE]
  > <span data-ttu-id="56287-113">Das Schlüsselwort `global` ist nur dann der globale Namespacealias, wenn es sich um den linken Bezeichner des `::`-Qualifizierers handelt.</span><span class="sxs-lookup"><span data-stu-id="56287-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="56287-114">Sie können auch das [`.`-Token](member-access-operators.md#member-access-expression-) verwenden, um auf einen Member eines Namespace mit Alias zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="56287-114">You can also use the [`.` token](member-access-operators.md#member-access-expression-) to access a member of an aliased namespace.</span></span> <span data-ttu-id="56287-115">Allerdings wird das `.`-Token auch verwendet, um auf einen Typmember zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="56287-115">However, the `.` token is also used to access a type member.</span></span> <span data-ttu-id="56287-116">Der Qualifizierer `::` stellt sicher, dass sein linker Bezeichner immer auf einen Namespacealias verweist, selbst wenn ein Typ oder ein Namespace mit demselben Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="56287-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56287-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="56287-117">C# language specification</span></span>

<span data-ttu-id="56287-118">Weitere Informationen finden Sie im Abschnitt [Namespacealias-Qualifizierer](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="56287-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56287-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56287-119">See also</span></span>

- [<span data-ttu-id="56287-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="56287-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="56287-121">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="56287-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="56287-122">Verwenden von Namespaces</span><span class="sxs-lookup"><span data-stu-id="56287-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
