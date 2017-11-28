---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9dab9115c31e538bd28583b9f0591ae0c9611e2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Gibt an, dass eine Eigenschaft geschrieben, aber nicht gelesen werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="rules"></a>Regeln  
 **Deklarationskontext.** Sie können `WriteOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `WriteOnly` Eigenschaft muss eine Klasse, Struktur oder Modul, und eine Quelldatei, Namespace oder Prozedur nicht möglich.  
  
 Sie können deklarieren, dass eine Eigenschaft als `WriteOnly`, aber keine Variable.  
  
## <a name="when-to-use-writeonly"></a>WriteOnly verwenden  
 In einigen Fällen möchten Sie in der Lage, einen Wert festlegen, doch nicht zu ermitteln, was ist den verwendeten Code. Beispielsweise müssen vertrauliche Daten, z. B. eine Sozialversicherungsnummer oder ein Kennwort aus Access von keiner Komponente geschützt werden, die nicht für die festgelegt. In diesen Fällen können Sie eine `WriteOnly` Eigenschaft zum Festlegen des Werts.  
  
> [!IMPORTANT]
>  Wenn Sie definieren und verwenden eine `WriteOnly` -Eigenschaft, sollten Sie die folgenden zusätzlichen Schutzmaßnahmen:  
  
-   **Überschreiben.** Wenn die Eigenschaft auf einen Member einer Klasse ist, ermöglichen es standardmäßig [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), und nicht deklarieren `Overridable` oder `MustOverride`. Dadurch wird verhindert, dass eine abgeleitete Klasse unerwünschten Zugriff über eine Außerkraftsetzung.  
  
-   **Zugriffsebene.** Wenn Sie die Eigenschaft sensible Daten in eine oder mehrere Variablen enthalten, deklarieren Sie diese [Private](../../../visual-basic/language-reference/modifiers/private.md) , damit kein anderer Code darauf zugreifen kann.  
  
-   **Die Verschlüsselung.** Speichern Sie alle gespeicherten vertraulichen Daten in verschlüsselter Form anstatt im nur-Text. Bösartiger Code irgendwie Zugriff auf diesen Bereich des Arbeitsspeichers erlangt, ist es schwieriger zu stellen der Daten verwenden. Verschlüsselung ist auch hilfreich, wenn es erforderlich, um die sensiblen Daten zu serialisieren.  
  
-   **Zurücksetzen.** Wenn die Klasse, Struktur oder Modul, definieren die Eigenschaft wird beendet, die sensiblen Daten auf Standardwerte oder andere bedeutungslose Werte zurücksetzen. Dies bietet zusätzlichen Schutz, wenn Sie diesen Bereich des Arbeitsspeichers für den allgemeinen Zugriff freigegeben wird.  
  
-   **Dauerhaftigkeit.** Beibehalten Sie vertraulichen Daten, z. B. auf dem Datenträger nicht, wenn Sie dies vermeiden können. Schreiben Sie auch nicht vertraulichen Daten in die Zwischenablage.  
  
 Die `WriteOnly` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
