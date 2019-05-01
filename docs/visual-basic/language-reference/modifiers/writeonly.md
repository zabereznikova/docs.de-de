---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 1b8de27e872914ba59d73126d2a9a7c42609165e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051818"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Gibt an, dass eine Eigenschaft geschrieben, jedoch nicht gelesen werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="rules"></a>Regeln  
 **Deklarationskontext.** Sie können `WriteOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `WriteOnly` Eigenschaft muss eine Klasse, Struktur oder Modul, und eine Quelldatei, Namespace oder Prozedur nicht möglich.  
  
 Sie können deklarieren, dass eine Eigenschaft als `WriteOnly`, aber keine Variable.  
  
## <a name="when-to-use-writeonly"></a>WriteOnly-Verwendung  
 Gelegentlich möchten Sie den verwendeten Code in der Lage, einen Wert festlegen, aber nicht zu ermitteln, was es ist. Sensible Daten, z. B. eine Sozialversicherungsnummer oder ein Kennwort, müssen z. B. Zugriff von einer beliebigen Komponente geschützt werden müssen, die ihn nicht festgelegt. In diesen Fällen können Sie eine `WriteOnly` Eigenschaft zum Festlegen des Werts.  
  
> [!IMPORTANT]
>  Wenn Sie definieren und Verwenden einer `WriteOnly` -Eigenschaft, sollten Sie die folgenden zusätzlichen Schutzmaßnahmen:  
  
- **Überschreiben.** Wenn die Eigenschaft auf einen Member einer Klasse ist, können sie standardmäßig [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), und nicht deklarieren `Overridable` oder `MustOverride`. Dadurch wird verhindert, dass eine abgeleitete Klasse unerwünschten Zugriff über eine Außerkraftsetzung.  
  
- **Zugriffsebene.** Wenn Sie vertrauliche Daten von der Eigenschaft in eine oder mehrere Variablen enthalten, deklarieren sie [Private](../../../visual-basic/language-reference/modifiers/private.md) , damit kein anderer Code darauf zugreifen kann.  
  
- **Verschlüsselung.** Store Sie alle vertrauliche Daten in verschlüsselter Form und nicht im nur-Text. Wenn Schadsoftware aus irgendeinem Grund den Zugriff auf diesen Bereich des Arbeitsspeichers hinzugefügt werden, ist es schwieriger, stellen die Daten verwenden. Verschlüsselung ist auch nützlich, wenn es erforderlich, um die sensiblen Daten zu serialisieren ist.  
  
- **Das Zurücksetzen.** Wenn die Klasse, Struktur oder Module, die die Eigenschaft wird beendet, die sensiblen Daten zurückzusetzen, auf die Standardwerte oder in andere Werte ohne Bedeutung. Dies bietet zusätzlichen Schutz, wenn dieser Bereich des Arbeitsspeichers für den allgemeinen Zugriff freigegeben wird.  
  
- **Dauerhaftigkeit.** Erhalten Sie vertraulichen Daten, z. B. auf dem Datenträger bleiben nicht werden, wenn Sie es vermeiden können. Schreiben Sie auch nicht sensiblen Daten in die Zwischenablage.  
  
 Die `WriteOnly` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
