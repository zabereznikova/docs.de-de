---
title: Spät gebundene Auflösung. Laufzeitfehler sind möglich.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 1c7b352c7bd61216ecce9901585945e740428ee3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873864"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Spät gebundene Auflösung. Laufzeitfehler sind möglich.

Ein-Objekt wird einer Variablen zugewiesen, die als [Objekt Datentyp](../data-types/object-data-type.md)deklariert wird.  
  
 Wenn Sie eine Variable als deklarieren `Object` , muss der Compiler die *späte Bindung*durchführen, die zur Laufzeit zusätzliche Vorgänge verursacht. Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus. Wenn Sie z. b. <xref:System.Windows.Forms.Form> der Variablen eine zuweisen `Object` und dann versuchen, auf die- <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> Eigenschaft zuzugreifen, löst die Laufzeit eine <xref:System.MemberAccessException> aus, da die- <xref:System.Windows.Forms.Form> Klasse keine-Eigenschaft verfügbar macht `NameTable` .  
  
 Wenn Sie die Variable als einen bestimmten Typ deklarieren, kann der Compiler zum Zeitpunkt der Kompilierung eine *frühe Bindung* durchführen. Dies führt zu einer verbesserten Leistung, kontrolliertem Zugriff auf die Member des spezifischen Typs und besserer Lesbarkeit des Codes.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42017  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Deklarieren Sie die Variable nach Möglichkeit als einen bestimmten Typ.  
  
## <a name="see-also"></a>Weitere Informationen

- [Frühes und spätes Binden](../../programming-guide/language-features/early-late-binding/index.md)
- [Deklaration von Objektvariablen](../../programming-guide/language-features/variables/object-variable-declaration.md)
