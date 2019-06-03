---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379575"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>„iPad“ sollte in der Datei für benutzerdefinierte Funktionen nicht verwendet werden, da es sich dabei nun um eine Browserfunktion handelt

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 handelt es sich bei „iPad“ um einen Bezeichner in der ASP.NET-Standarddatei für Browserfunktionen, der deshalb nicht in einer Datei für benutzerdefinierte Funktionen verwendet werden sollte.|
|Vorschlag|Wenn bestimmte Funktionen von „iPad“ erforderlich sind, muss das Verhalten von „iPad“ geändert werden, indem die Funktionen auf dem vorab definierten Gateway auf „refID &quot;iPad&quot;“ festgelegt werden, statt eine neue ID für &quot;iPad&quot; durch Abgleich mit dem Benutzer-Agent zu generieren.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
