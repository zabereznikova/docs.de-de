---
description: using static-Anweisung – C#-Referenz
title: using static-Anweisung – C#-Referenz
ms.date: 03/10/2017
f1_keywords:
- using-static_CSharpKeyword
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: d117d4423a2f7c782cd6365a73e6c18298d89abc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162231"
---
# <a name="using-static-directive-c-reference"></a>using static-Anweisung (C#-Referenz)

Die `using static`-Anweisung legt einen Typ fest, auf dessen statische Member und geschachtelte Typen Sie ohne Angabe eines Typnamens zugreifen können. Die Syntax lautet:

```csharp
using static <fully-qualified-type-name>;
```

Hier steht *fully-qualified-type-name* für den Namen des Typs, auf dessen statische Member und geschachtelte Typen verwiesen werden kann, ohne einen Typnamen anzugeben. Wenn Sie keinen vollqualifizierten Typnamen angeben (der vollständige Namespacename zusammen mit dem Typnamen), generiert C# den Compilerfehler [CS0246](../compiler-messages/cs0246.md): Der Typ- oder Namespacename "type/namespace" konnte nicht gefunden werden (fehlt eine using-Direktive oder ein Assemblyverweis?).

Die `using static`-Anweisung gilt für jeden Typ, der über statische Member (oder geschachtelte Typen) verfügt, auch wenn er ebenfalls über Instanzmember verfügt. Instanzmember können jedoch nur über die Typinstanz aufgerufen werden.

Die `using static`-Direktive wurde in C# 6 eingeführt.

## <a name="remarks"></a>Hinweise

Wenn Sie einen statischen Member aufrufen, geben Sie normalerweise den Typnamen zusammen mit dem Membernamen an. Das wiederholte Eingeben desselben Typnamens zum Aufrufen von Membern dieses Typs kann zu ausführlichem, verwirrendem Code führen. Die folgende Definition einer `Circle`-Klasse verweist z.B. auf mehrere Member der Klasse <xref:System.Math>.

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

Da nicht mehr jedes Mal explizit auf die Klasse <xref:System.Math> verwiesen werden muss, wenn auf einen Member verwiesen wird, erzeugt die `using static`-Direktive deutlich übersichtlicheren Code:

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

`using static` importiert nur zugängliche statische Member und geschachtelte Typen, die im angegebenen Typ deklariert sind.  Geerbte Member werden nicht importiert.  Sie können aus jedem benannten Typen mit einer statischen using-Anweisung importieren, einschließlich Visual Basic-Module.  Wenn F#-Funktionen der obersten Ebene in den Metadaten als statische Member eines benannten Typs angezeigt werden, dessen Name ein gültiger C#-Bezeichner ist, können die F#-Funktionen importiert werden.

 `using static` macht Erweiterungsmethoden, die im angegebenen Typ deklariert sind, für die Erweiterungsmethodensuche verfügbar.  Die Namen der Erweiterungsmethoden werden jedoch bei nicht referenzierten Verweisen im Code nicht in den Bereich importiert.

 Methoden mit dem gleichen Namen, die aus verschiedenen Typen von verschiedenen statischen `using static`-Direktiven in der gleichen Kompilierungseinheit oder dem gleichen Namespace importiert wurden, bilden eine Methodengruppe.  Die Überladungsauflösung innerhalb dieser Methodengruppen folgt den normalen C#-Regeln.

## <a name="example"></a>Beispiel

Im folgenden Beispiele wird die `using static`-Direktive verwendet, um die statischen Member der Klassen <xref:System.Console>, <xref:System.Math> und <xref:System.String> zugänglich zu machen, ohne deren Typnamen angeben zu müssen.

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

In diesem Beispiel hätte die `using static`-Direktive auch auf den Typ <xref:System.Double> angewendet werden können. Dadurch wäre es möglich geworden, die Methode <xref:System.Double.TryParse(System.String,System.Double@)> aufzurufen, ohne einen Typnamen anzugeben. Hierdurch wird allerdings weniger lesbarer Code generiert, da die `using static`-Anweisungen überprüft werden müssen, um zu bestimmen, welche `TryParse`-Methode eines numerischen Typs aufgerufen wird.

## <a name="see-also"></a>Siehe auch

- [using-Anweisung](using-directive.md)
- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](index.md)
- [Using-Namespaces](../../programming-guide/namespaces/using-namespaces.md)
- [Namespaces](../../programming-guide/namespaces/index.md)
