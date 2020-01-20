---
title: 'Breaking-Change-Kategorien: .NET Core'
description: Erfahren Sie mehr über die Kategorisierung von Breaking Changes in .NET Core.
ms.date: 06/10/2019
ms.openlocfilehash: 32cf55dc3ba0b16bae8cfe6179211150b2c90e2c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343601"
---
# <a name="breaking-change-categories"></a>Breaking Change-Kategorien

*Kompatibilität* bezieht sich auf die Kompilierung oder Ausführung von Code in einer Version einer .NET-Implementierung, die nicht mit dem ursprünglich entwickelten Code zusammenhängt. Eine bestimmte Änderung kann die Kompatibilität auf sechs verschiedene Arten beeinträchtigen. Die [einzelnen Arten von Änderungen](index.md), die beim Auswerten der Kompatibilität berücksichtigt werden, fallen unter die folgenden Kategorien:

- [Verhaltensänderung](#behavioral-change)
- [Binärkompatibilität](#binary-compatibility)
- [Quellkompatibilität](#source-compatibility)
- [Entwurfszeitkompatibilität](#design-time-compatibility)
- [Abwärtskompatibilität](#backwards-compatibility)
- [Aufwärtskompatibilität](#forward-compatibility) (kein Ziel von .NET Core)

## <a name="behavioral-change"></a>Behavior Change

Ein Behavior Change stellt eine Verhaltensänderung eines Members dar. Die Änderung kann extern sichtbar sein (eine Methode kann beispielsweise eine andere Ausnahme auslösen) oder eine geänderte Implementierung darstellen (beispielsweise eine Änderung in der Art und Weise, wie ein Rückgabewert berechnet wird, das Hinzufügen oder Entfernen interner Methodenaufrufe oder sogar eine beträchtliche Leistungsverbesserung).

Wenn Behavior Changes extern sichtbar sind und der öffentliche Vertrag eines Typs geändert wird, können sie leicht ausgewertet werden, da sie sich auf die binäre Kompatibilität auswirken. Das Auswerten von Implementierungsänderungen ist weitaus schwieriger. Abhängig von der Art der Änderung und der Häufigkeit und der Verwendungsmuster der API können die Auswirkungen einer Änderung von harmlos bis schwerwiegend reichen.

## <a name="binary-compatibility"></a>Binärkompatibilität

Die Binärkompatibilität bezieht sich auf die Fähigkeit eines Consumers einer API, diese API in einer neueren Version ohne Neukompilierung zu verwenden. Änderungen wie das Hinzufügen von Methoden oder einer neuen Schnittstellenimplementierung zu einem Typ wirken sich nicht auf die Binärkompatibilität aus. Das Entfernen oder Ändern der öffentlichen Signaturen einer Assembly, sodass Consumer nicht mehr auf dieselbe von der Assembly verfügbar gemachte Schnittstelle zugreifen können, wirkt sich auf die binäre Kompatibilität aus. Eine Änderung dieser Art wird als *inkompatible Binäränderung* bezeichnet.

## <a name="source-compatibility"></a>Quellkompatibilität

Die Quellkompatibilität bezieht sich auf die Fähigkeit vorhandener Consumer einer API, die Neukompilierung für eine neuere Version ohne Quelländerungen vorzunehmen. Eine *inkompatible Quelländerung* tritt auf, wenn ein Consumer den Quellcode ändern muss, damit er erfolgreich für eine neuere Version einer API erstellt werden kann.

## <a name="design-time-compatibility"></a>Entwurfszeitkompatibilität

Die Entwurfszeitkompatibilität bezieht sich auf die Beibehaltung der Entwurfszeit in verschiedenen Versionen von Visual Studio und anderen Entwurfszeitumgebungen. Dies kann zwar das Verhalten oder die Benutzeroberfläche von Designern einschließen, der wichtigste Aspekt der Entwurfszeitkompatibilität betrifft aber die Projektkompatibilität. Ein Projekt oder eine Lösung muss in einer neueren Version der Entwurfszeitumgebung geöffnet und verwendet werden können.

## <a name="backwards-compatibility"></a>Abwärtskompatibilität

Die Abwärtskompatibilität bezieht sich auf die Fähigkeit, dass ein vorhandener Consumer einer API für eine neue Version ausgeführt werden kann, während er sich auf die gleiche Weise verhält. Sowohl Behavior Changes als auch Änderungen in der Binärkompatibilität beeinflussen die Abwärtskompatibilität. Wenn ein Consumer nicht für die neuere Version der API ausgeführt werden kann oder sich anders verhält, ist die API *abwärtskompatibel*.

Da Entwickler in neueren Versionen einer API Abwärtskompatibilität erwarten, wird von Änderungen abgeraten, die sich auf die Abwärtskompatibilität auswirken.

## <a name="forward-compatibility"></a>Aufwärtskompatibilität

Die Aufwärtskompatibilität bezieht sich auf die Fähigkeit, dass ein vorhandener Consumer einer API für eine ältere Version ausgeführt werden kann, während er sich auf die gleiche Weise verhält. Wenn ein Consumer nicht für eine ältere Version der API ausgeführt werden kann oder sich anders verhält, ist die API *aufwärtskompatibel*.

Durch die Beibehaltung der Aufwärtskompatibilität werden alle Änderungen oder Ergänzungen von Version zu Version praktisch ausgeschlossen, da diese Änderungen verhindern, dass ein Consumer, der eine höhere Version als Ziel hat, unter einer früheren Version ausgeführt wird. Entwickler erwarten, dass ein Consumer, der auf einer neueren API basiert, möglicherweise nicht ordnungsgemäß mit der älteren API funktioniert.

Die Beibehaltung der Aufwärtskompatibilität ist kein Ziel von .NET Core.

## <a name="see-also"></a>Siehe auch

- [Bewerten von Breaking Changes in .NET Core](index.md)
