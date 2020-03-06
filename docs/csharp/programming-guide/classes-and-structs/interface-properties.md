---
title: Schnittstelleneigenschaften – C#-Programmierhandbuch
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626619"
---
# <a name="interface-properties-c-programming-guide"></a>Schnittstelleneigenschaften (C#-Programmierhandbuch)

Eigenschaften können für eine [Schnittstelle](../../language-reference/keywords/interface.md) deklariert werden. Im folgenden Beispiel wird eine Zugriffsmethode für Schnittstelleneigenschaften deklariert:

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

Schnittstelleneigenschaften verfügen in der Regel über keinen Text. Die Zugriffsmethoden geben an, ob Lese-/Schreibzugriff auf die Eigenschaft besteht oder ob sie schreib- oder lesegeschützt ist. Anders als bei Klassen und Strukturen wird beim Deklarieren von Zugriffsmethoden ohne Text keine [automatisch implementierte Eigenschaft](auto-implemented-properties.md) deklariert. Ab C# 8.0 kann eine Schnittstelle eine Standardimplementierung für Member, einschließlich Eigenschaften, definieren. Standardimplementierungen für Eigenschaften in einer Schnittstelle sind selten, weil Schnittstellen möglicherweise keine Instanzdatenfelder definieren.

## <a name="example"></a>Beispiel

In diesem Beispiel besitzt die Schnittstelle `IEmployee` eine Lese-/Schreibzugriff-Eigenschaft `Name` und eine Lesezugriff-Eigenschaft `Counter`. Die Klasse `Employee` implementiert die Schnittstelle `IEmployee` und verwendet diese beiden Eigenschaften. Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Mitarbeiteranzahl werden angezeigt.

Sie können den vollqualifizierten Namen der Eigenschaft verwenden, der auf die Schnittstelle verweist, in der der Member deklariert wird. Zum Beispiel:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

Im vorangehenden Beispiel wird die [Explizite Schnittstellenimplementierung](../interfaces/explicit-interface-implementation.md) veranschaulicht. Wenn z.B. die Klasse `Employee` die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen die Eigenschaft `Name` besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich. Das bedeutet, dass die folgende Eigenschaftendeklaration:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

die Eigenschaft `Name` für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

die Eigenschaft `Name` für die Schnittstelle `ICitizen`.

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a>Beispielausgabe:

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Eigenschaften](./properties.md)
- [Verwenden von Eigenschaften](./using-properties.md)
- [Vergleich zwischen Eigenschaften und Indexern](../indexers/comparison-between-properties-and-indexers.md)
- [Indexer](../indexers/index.md)
- [Schnittstellen](../interfaces/index.md)
