---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617533"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen

#### <a name="details"></a>Details

Unter bestimmten Umständen können Aufrufe der internen Methode **System.Windows.Intput.PenContext.Disable** auf touchfähigen Systemen eine nicht behandelte `T:System.ArgumentException` aufgrund von Eintrittsinvarianz auslösen.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.7 behoben. Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.1       |
| Typ    | Neuzuweisung |
