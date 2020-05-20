---
title: Kulturunabhängige Zeichenfolgenoperationen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
ms.openlocfilehash: 06c46033936e16355b8d2eb6650e8731a04af6e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141276"
---
# <a name="culture-insensitive-string-operations"></a>Kulturunabhängige Zeichenfolgenoperationen

Kulturabhängige Zeichenfolgenoperationen können von Vorteil sein, wenn Sie Anwendungen erstellen, mit denen Benutzern Ergebnisse auf Kulturbasis angezeigt werden. In der Standardeinstellung rufen kulturabhängige Methoden die zu verwendende Kultur aus der <xref:System.Globalization.CultureInfo.CurrentCulture%2A>-Eigenschaft für den aktuellen Thread ab.

Kulturabhängige Zeichenfolgenoperationen stellen jedoch nicht immer das gewünschte Verhalten dar. Die Verwendung von kulturabhängigen Operationen in Szenarien, in denen die Ergebnisse unabhängig von der Kultur sein sollen, kann bei Kulturen mit speziellen Groß- und Kleinschreibungs- und Sortierungsregeln zum Fehlschlagen des Anwendungscodes führen. Ein Beispiel finden Sie im Artikel [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET](../../../docs/standard/base-types/best-practices-strings.md) im Abschnitt [Zeichenfolgenvergleiche mit der aktuellen Kultur](../../../docs/standard/base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture).

Die zu verwendenden Zeichenfolgenoperationen (kulturabhängig oder -unabhängig) richten sich danach, wie die Ergebnisse von der Anwendung verwendet werden. Zeichenfolgenoperationen, die dem Benutzer Ergebnisse anzeigen, sollten i. d. R. kulturabhängig sein. Wenn eine Anwendung in einem Listenfeld z. B. eine sortierte Liste lokalisierter Zeichenfolgen anzeigt, sollte die Anwendung eine kulturabhängige Sortierung durchführen.

Ergebnisse von intern verwendeten Zeichenfolgenoperationen, sollten i. d. R. kulturunabhängig sein. Ergebnisse von Zeichenfolgenoperationen sollten sich im Allgemeinen nicht von Kultur zu Kultur unterscheiden, wenn die Anwendung Dateinamen, Persistenzformate oder Symbolinformationen verwendet, die dem Benutzer nicht angezeigt werden. Wenn eine Anwendung z. B. einen Vergleich durchführt, um festzustellen, ob es sich um ein anerkanntes XML-Tag handelt, sollte der Vergleich kulturunabhängig sein. Wenn darüber hinaus eine Sicherheitsentscheidung auf dem Ergebnis eines Zeichenfolgenvergleichs oder einer Änderung der Groß-/Kleinschreibung beruht, sollte die Operation kulturunabhängig sein, um sicherzustellen, dass das Ergebnis nicht durch den Wert von <xref:System.Globalization.CultureInfo.CurrentCulture%2A> beeinflusst wird.

Unabhängig davon, ob die von Ihnen entwickelte Anwendung Code zur Behandlung von Lokalisierungs- und Globalisierungsproblemen enthält, müssen Sie die .NET Framework-Methoden kennen, die in der Standardeinstellung kulturabhängige Ergebnisse abrufen. Aus diesem Grund wird in diesem Thema erläutert, wie die Anwendungen diese Methoden ordnungsgemäß verwenden, um kulturunabhängige Ergebnisse zu erhalten.

## <a name="see-also"></a>Weitere Informationen

- [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)
