---
title: WriteOnly
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
ms.openlocfilehash: 847617ea6534089857a759fbea3bb16a3a5a36a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344191"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Gibt an, dass eine Eigenschaft geschrieben, jedoch nicht gelesen werden kann.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="rules"></a>Regeln  
 **Deklarations Kontext.** Sie können `WriteOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für eine `WriteOnly` Eigenschaft eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.  
  
 Sie können eine Eigenschaft als `WriteOnly`deklarieren, aber keine Variable.  
  
## <a name="when-to-use-writeonly"></a>Verwendung von "schreibgeschützt"  
 Manchmal möchten Sie, dass der verarbeitende Code einen Wert festlegen kann, aber nicht ermitteln kann, was er ist. Sensible Daten, z. b. eine Sozialversicherungsnummer oder ein Kennwort, müssen z. b. vor dem Zugriff durch eine beliebige Komponente geschützt werden, die Sie nicht festgelegt hat. In diesen Fällen können Sie eine `WriteOnly`-Eigenschaft verwenden, um den Wert festzulegen.  
  
> [!IMPORTANT]
> Wenn Sie eine `WriteOnly`-Eigenschaft definieren und verwenden, sollten Sie die folgenden zusätzlichen Schutzmaßnahmen in Erwägung gezogen haben:  
  
- **Dende.** Wenn die Eigenschaft ein Member einer Klasse ist, lassen Sie die Standardeinstellung [nodeverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)zu, und deklarieren Sie Sie nicht `Overridable` oder `MustOverride`. Dadurch wird verhindert, dass eine abgeleitete Klasse den unerwünschten Zugriff über eine außer Kraft Setzung ermöglicht.  
  
- **Zugriffsebene.** Wenn Sie die sensiblen Daten der Eigenschaft in einer oder mehreren Variablen speichern, deklarieren Sie diese als [Privat](../../../visual-basic/language-reference/modifiers/private.md) , sodass kein anderer Code darauf zugreifen kann.  
  
- **Verschlüsselungs.** Speichern Sie alle sensiblen Daten in verschlüsselter Form und nicht als Klartext. Wenn bösartiger Code auf diese Weise Zugriff auf diesen Speicherbereich erlangt, ist es schwieriger, die Daten zu verwenden. Die Verschlüsselung ist auch dann nützlich, wenn es erforderlich ist, die sensiblen Daten zu serialisieren.  
  
- **Zurücksetzen.** Wenn die Klasse, Struktur oder das Modul, das die Eigenschaft definiert, beendet wird, setzen Sie die sensiblen Daten auf die Standardwerte oder auf andere bedeutungslose Werte zurück. Dies bietet zusätzlichen Schutz, wenn dieser Speicherbereich für den allgemeinen Zugriff freigegeben wird.  
  
- **Persistenz.** Bewahren Sie keine sensiblen Daten auf, z. b. auf dem Datenträger, wenn Sie dies vermeiden können. Schreiben Sie außerdem keine sensiblen Daten in die Zwischenablage.  
  
 Der `WriteOnly` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
