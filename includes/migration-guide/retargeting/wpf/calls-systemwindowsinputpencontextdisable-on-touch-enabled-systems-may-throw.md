---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887776"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen

|   |   |
|---|---|
|Details|Unter bestimmten Umständen können Aufrufe der internen Methode **System.Windows.Intput.PenContext.Disable** auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.7 behoben. Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.|
|Bereich|Microsoft Edge|
|Version|4.6.1|
|Typ|Neuzuweisung|
