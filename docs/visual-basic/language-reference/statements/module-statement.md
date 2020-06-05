---
title: Module-Anweisung
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 24a27ba41f5ac889f2f2725a2852368a4292a6fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404453"
---
# <a name="module-statement"></a>Module-Anweisung

Deklariert den Namen eines Moduls und führt die Definition der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, die das Modul umfasst.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a>Bestandteile

`attributelist`  
Optional. Siehe [Attribut Liste](attribute-list.md).

`accessmodifier`  
Optional. Kann eines der folgenden Elemente sein:

- [Öffentlich](../modifiers/public.md)

- [Kollegen](../modifiers/friend.md)

Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

`name`  
Erforderlich. Der Name dieses Moduls. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

`statements`  
Optional. Anweisungen, die die Variablen, Eigenschaften, Ereignisse, Prozeduren und die Typen dieses Moduls definieren.

`End Module`  
Beendet die `Module`-Definition.

## <a name="remarks"></a>Bemerkungen

Eine- `Module` Anweisung definiert einen Referenztyp, der im gesamten Namespace verfügbar ist. Ein *Modul* (manchmal auch als *Standardmodul*bezeichnet) ähnelt einer Klasse, jedoch mit einigen wichtigen unterschieden. Jedes Modul verfügt über genau eine Instanz und muss weder erstellt noch einer Variablen zugewiesen werden. Module unterstützen keine Vererbung oder Implementierung von Schnittstellen. Beachten Sie, dass ein Modul kein *Typ* in dem Sinn ist, dass eine Klasse oder Struktur ist – Sie können kein Programmier Element deklarieren, um den Datentyp eines Moduls zu erhalten.

Sie können `Module` nur auf Namespace Ebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für ein Modul eine Quelldatei oder ein Namespace sein muss und weder eine Klasse noch eine Struktur, ein Modul, eine Schnittstelle, eine Prozedur oder einen Block sein kann. Sie können ein Modul nicht in einem anderen Modul oder in einem beliebigen Typ Schachteln. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Ein Modul hat die gleiche Lebensdauer wie das Programm. Da ihre Member alle sind `Shared` , haben Sie auch die Lebensdauer, die der des Programms entspricht.

Module haben standardmäßig den [Friend](../modifiers/friend.md) -Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Alle Member eines Moduls sind implizit `Shared` .

## <a name="classes-and-modules"></a>Klassen und Module

Diese Elemente weisen viele Ähnlichkeiten auf, aber es gibt auch einige wichtige Unterschiede.

- **Begriffs.** In früheren Versionen von Visual Basic werden zwei Arten von Modulen erkannt: *Klassen Module* (CLS-Dateien) und *Standardmodule* (Bas-Dateien). Mit der aktuellen Version werden diese *Klassen* bzw. *Module*aufgerufen.

- **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse ein frei Gegebenes oder ein Instanzmember ist.

- **Objekt Ausrichtung.** Klassen sind objektorientiert, aber Module sind nicht. Daher können nur Klassen als Objekte instanziiert werden. Weitere Informationen finden Sie unter [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md).

## <a name="rules"></a>Regeln

- **Modifizierer.** Alle Modulmember werden implizit frei [gegeben](../modifiers/shared.md). Sie können das- `Shared` Schlüsselwort nicht verwenden, wenn Sie einen Member deklarieren, und Sie können den freigegebenen Status eines beliebigen Members nicht ändern.

- **Vererbung.** Ein Modul kann nicht von einem anderen Typ als Erben <xref:System.Object> , von dem alle Module erben. Insbesondere kann ein Modul nicht von einem anderen Modul erben.

  Die [erbt-Anweisung](inherits-statement.md) kann nicht in einer Modul Definition verwendet werden, auch um anzugeben <xref:System.Object> .

- **Standard Eigenschaft.** In einem Modul können keine Standardeigenschaften definiert werden. Weitere Informationen finden Sie unter [default (Standard](../modifiers/default.md)).

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Innerhalb eines Moduls können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. Modul Elemente haben standardmäßig den [öffentlichen](../modifiers/public.md) Zugriff, mit Ausnahme von Variablen und Konstanten, die standardmäßig den [privaten](../modifiers/private.md) Zugriff haben. Wenn ein Modul über einen eingeschränkteren Zugriff als einen seiner Mitglieder verfügt, hat die angegebene Modul Zugriffsebene Vorrang.

- **Umfang.** Ein Modul befindet sich im gesamten Namespace im Gültigkeitsbereich.

  Der Gültigkeitsbereich jedes Modulmembers ist das gesamte Modul. Beachten Sie, dass alle Member eine *typherauf*Stufung durchlaufen, was bewirkt, dass Ihr Bereich in den Namespace herauf gestuft wird, der das Modul enthält. Weitere Informationen finden Sie unter [Typerweiterung](../../programming-guide/language-features/declared-elements/type-promotion.md).

- **Abschluss.** Sie können über mehrere Module in einem Projekt verfügen, und Sie können in zwei oder mehr Modulen Member mit demselben Namen deklarieren. Sie müssen allerdings einen beliebigen Verweis auf ein solches Element mit dem entsprechenden Modulnamen qualifizieren, wenn der Verweis von außerhalb dieses Moduls liegt. Weitere Informationen finden Sie unter [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="example"></a>Beispiel

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a>Weitere Informationen

- [Class-Anweisung](class-statement.md)
- [Namespace-Anweisung](namespace-statement.md)
- [Structure Statement](structure-statement.md)
- [Interface-Anweisung](interface-statement.md)
- [Property Statement](property-statement.md)
- [Typerweiterung](../../programming-guide/language-features/declared-elements/type-promotion.md)
