---
title: sizeof – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 8bb6d4a37b2eea3060921937cf15a1fdd1be97b4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634014"
---
# <a name="sizeof-c-reference"></a>sizeof (C#-Referenz)

Wird verwendet, um die Größe eines nicht verwalteten Typs in Bytes abzurufen.

Zu nicht verwalteten Typen zählen die folgenden:

- Die einfachen Typen, die in der folgenden Tabelle aufgelistet werden:

   |Ausdruck|Konstanter Wert|
   |----------------|--------------------|
   |`sizeof(sbyte)`|1|
   |`sizeof(byte)`|1|
   |`sizeof(short)`|2|
   |`sizeof(ushort)`|2|
   |`sizeof(int)`|4|
   |`sizeof(uint)`|4|
   |`sizeof(long)`|8|
   |`sizeof(ulong)`|8|
   |`sizeof(char)`|2 (Unicode)|
   |`sizeof(float)`|4|
   |`sizeof(double)`|8|
   |`sizeof(decimal)`|16|
   |`sizeof(bool)`|1|

- Enumerationstypen.

- Zeigertypen.

- Benutzerdefinierte Strukturen, die keine Instanzenfelder oder automatisch implementierten Instanzeigenschaften enthalten, bei denen es sich um Verweistypen oder konstruierte Typen handelt.

Im folgenden Beispiel wird gezeigt, wie Sie die Größe von `int` abrufen:

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a>Anmerkungen

Ab C# Version 2.0 ist für die Anwendung von `sizeof` auf einfache Typen oder Enumerationstypen nicht mehr erforderlich, dass Code in [unsicherem](unsafe.md) Kontext kompiliert wird.

Operator `sizeof` kann nicht überladen werden. Die Rückgabewerte des Operators `sizeof` sind vom Typ `int`. Die vorherige Tabelle zeigt die konstanten Werte, die als Ersatz für `sizeof`-Ausdrücke dienen, die über bestimmte einfache Typen als Operanden verfügen.

Bei allen anderen Typen, darunter Strukturen, kann der Operator `sizeof` nur in unsicheren Codeblöcken zugelassen werden. Sie können die Methode <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> zwar verwenden, der von dieser Methode zurückgegebene Wert entspricht allerdings nicht immer dem von `sizeof` zurückgegeben Wert. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> gibt die Größe nach dem Marshalling des Typs zurück, während `sizeof` die Größe inklusive Abständen zurückgibt, die von der Common Language Runtime zugeordnet wurde.

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Operatorschlüsselwörter](operator-keywords.md)
- [enum](enum.md)
- [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md)
- [Strukturen](../../programming-guide/classes-and-structs/structs.md)
- [Konstanten](../../programming-guide/classes-and-structs/constants.md)
