---
title: "WriteOnly (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "WriteOnly"
  - "vb.WriteOnly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "write-only properties"
  - "WriteOnly keyword"
  - "sensitive data, protecting"
  - "properties [Visual Basic], write-only"
  - "sensitive data"
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# WriteOnly (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass eine Eigenschaft geschrieben, aber nicht gelesen werden kann.  
  
## Hinweise  
  
## Regeln  
 **Deklarationskontext.** `WriteOnly` kann nur auf Modulebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für eine `WriteOnly`\-Eigenschaft eine Klasse, eine Struktur oder ein Modul sein muss und keine Quelldatei, kein Namespace und keine Prozedur sein kann.  
  
 Eine Eigenschaft kann als `WriteOnly` deklariert werden, eine Variable dagegen nicht.  
  
## Verwendung von WriteOnly  
 Manchmal soll der verwendete Code in der Lage sein, einen Wert festzulegen, aber er soll nicht ermitteln können, wie der Wert lautet.  Beispielsweise müssen vertrauliche Daten, z. B. eine Sozialversicherungsnummer oder ein Kennwort, vor dem Zugriff jeglicher Komponenten geschützt werden, die diese Daten nicht festgelegt haben.  In diesen Fällen können Sie eine `WriteOnly`\-Eigenschaft verwenden, um den Wert festzulegen.  
  
> [!IMPORTANT]
>  Bei der Definition und Verwendung einer `WriteOnly`\-Eigenschaft müssen die folgenden zusätzlichen Schutzmaßnahmen berücksichtigt werden:  
  
-   **Überschreiben.** Falls die Eigenschaft Member einer Klasse ist, lassen Sie zu, dass sie standardmäßig als [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) definiert ist, und deklarieren Sie sie nicht als `Overridable` oder `MustOverride`.  Damit wird verhindert, dass eine abgeleitete Klasse durch eine Überschreibung unerwünschten Zugriff erhält.  
  
-   **Zugriffsebene.** Wenn die sicherheitsrelevanten Daten der Eigenschaft in einer oder mehreren Variablen gespeichert werden, deklarieren Sie diese als [Private](../../../visual-basic/language-reference/modifiers/private.md), damit kein anderer Code auf diese Daten zugreifen kann.  
  
-   **Verschlüsselung.** Speichern Sie alle vertraulichen Daten in verschlüsselter Form statt als reinen Text.  Wenn böswilliger Code irgendwie Zugriff auf diesen Speicherbereich erhält, ist es schwieriger, von den Daten Gebrauch zu machen.  Verschlüsselung ist auch hilfreich, wenn es notwendig ist, die vertraulichen Daten zu serialisieren.  
  
-   **Zurücksetzen.** Wenn die Klasse, die Struktur oder das Modul, in der bzw. dem die Struktur definiert wird, beendet wird, setzen Sie die vertraulichen Daten auf Standardwerte oder andere bedeutungslose Werte zurück.  Dies bietet zusätzlichen Schutz, wenn dieser Speicherbereich für einen allgemeinen Zugriff freigegeben wird.  
  
-   **Dauerhaftigkeit.** Speichern Sie nach Möglichkeit vertrauliche Daten nicht permanent, z. B. auf Datenträgern.  Fügen Sie auch keine vertraulichen Daten in die Zwischenablage ein.  
  
 Der `WriteOnly`\-Modifizierer kann im folgenden Kontext verwendet werden:  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Siehe auch  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)