---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887776"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen

|   |   |
|---|---|
|Details|Unter bestimmten Umständen können Aufrufe der internen Methode **System.Windows.Intput.PenContext.Disable** auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.7 behoben. Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.|
|`Scope`|Edge|
|Version|4.6.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
