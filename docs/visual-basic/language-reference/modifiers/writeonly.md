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
ms.openlocfilehash: a9fa0a3a23561215d6ff122bc8e609b68ca6fc30
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386633"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Gibt an, dass eine Eigenschaft geschrieben, jedoch nicht gelesen werden kann.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="rules"></a>Regeln  
 **Deklarationskontext.** Sie können `WriteOnly` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für eine `WriteOnly` Eigenschaft eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.  
  
 Sie können eine Eigenschaft als `WriteOnly` , jedoch nicht als Variable deklarieren.  
  
## <a name="when-to-use-writeonly"></a>Verwendung von "schreibgeschützt"  
 Manchmal möchten Sie, dass der verarbeitende Code einen Wert festlegen kann, aber nicht ermitteln kann, was er ist. Sensible Daten, z. b. eine Sozialversicherungsnummer oder ein Kennwort, müssen z. b. vor dem Zugriff durch eine beliebige Komponente geschützt werden, die Sie nicht festgelegt hat. In diesen Fällen können Sie eine-Eigenschaft verwenden, `WriteOnly` um den Wert festzulegen.  
  
> [!IMPORTANT]
> Wenn Sie eine Eigenschaft definieren und verwenden `WriteOnly` , sollten Sie die folgenden zusätzlichen Schutzmaßnahmen beachten:  
  
- **Dende.** Wenn die Eigenschaft ein Member einer Klasse ist, lassen Sie die Standardeinstellung [nodeverridable](notoverridable.md)zu, und deklarieren Sie Sie nicht `Overridable` oder `MustOverride` . Dadurch wird verhindert, dass eine abgeleitete Klasse den unerwünschten Zugriff über eine außer Kraft Setzung ermöglicht.  
  
- **Zugriffsebene.** Wenn Sie die sensiblen Daten der Eigenschaft in einer oder mehreren Variablen speichern, deklarieren Sie diese als [Privat](private.md) , sodass kein anderer Code darauf zugreifen kann.  
  
- **Verschlüsselungs.** Speichern Sie alle sensiblen Daten in verschlüsselter Form und nicht als Klartext. Wenn bösartiger Code auf diese Weise Zugriff auf diesen Speicherbereich erlangt, ist es schwieriger, die Daten zu verwenden. Die Verschlüsselung ist auch dann nützlich, wenn es erforderlich ist, die sensiblen Daten zu serialisieren.  
  
- **Zurücksetzen.** Wenn die Klasse, Struktur oder das Modul, das die Eigenschaft definiert, beendet wird, setzen Sie die sensiblen Daten auf die Standardwerte oder auf andere bedeutungslose Werte zurück. Dies bietet zusätzlichen Schutz, wenn dieser Speicherbereich für den allgemeinen Zugriff freigegeben wird.  
  
- **Persistenz.** Bewahren Sie keine sensiblen Daten auf, z. b. auf dem Datenträger, wenn Sie dies vermeiden können. Schreiben Sie außerdem keine sensiblen Daten in die Zwischenablage.  
  
 Der- `WriteOnly` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Property Statement](../statements/property-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [ReadOnly](readonly.md)
- [Privat](private.md)
- [Schlüsselwörter](../keywords/index.md)
