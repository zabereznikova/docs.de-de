---
title: Verwalten von .NET Core-Installationen
description: Verwalten Sie mehrere Versionen von .NET Core SDK und Runtime auf Ihrem Computer, und arbeiten Sie dabei mit den Strategien für parallele Installationen.
author: leecow
ms.author: wiwagn
ms.date: 08/22/2018
ms.openlocfilehash: 06c3f43e7917efb8fd31898044d8f5d920c2cada
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485460"
---
# <a name="manage-net-core-installations"></a>Verwalten von .NET Core-Installationen

Mit .NET Core können mehrere SDK- und Runtime-Versionen parallel existieren. Dadurch wird bei der Erstellung und Ausführung von .NET Core-Anwendungen eine Flexibilität in der Versionsabhängigkeit ermöglicht. Dieses Installations- und Rollforwardverhalten automatischer Versionen bietet wertvolle Vorteile, jedoch auch einen wesentlichen Nachteil. Während der Installation von Updates des .NET Core SDK oder der .NET Core-Runtime bleiben frühere Versionen auf dem Datenträger. Durch mehrere installierte Versionen wird im Verlauf der Zeit die Datenträgerauslastung erhöht. Es wurden mehr als 50 .NET Core SDK-Updates veröffentlicht. Möglicherweise sind auf Ihrem System viele Versionen des SDK und der Runtime installiert, die entfernt werden könnten.

## <a name="safe-to-remove"></a>Ist das Entfernen sicher?

Durch das Verhalten bei der [.NET Core-Versionsauswahl](selection.md) und die Laufzeitkompatibilität von .NET Core zwischen Updates können frühere Versionen sicher entfernt werden. Updates für die .NET Core-Runtime sind innerhalb des „Bereichs“ einer Hauptversion kompatibel, wie z.B. 1.x und 2.x. Darüber hinaus können in neueren Versionen des .NET Core SDK in der Regel Anwendungen erstellt werden, die mit früheren Versionen der Laufzeit kompatibel sind.

Im Allgemeinen benötigen Sie nur das neueste SDK und die neueste Patchversion der Laufzeiten, die für Ihre Anwendung erforderlich sind. Instanzen mit älteren SDK- oder Runtime-Versionen beinhalten die Verwaltung von auf „project.json“ basierenden Anwendungen.  Sie können ältere Versionen sicher entfernen, wenn Ihre Anwendung keine bestimmten Gründe für frühere SDKs oder Laufzeiten aufweist.

Die Methoden zum Entfernen von .NET Core variieren je nach Plattform und haben sich über die .NET Core-Versionen hinweg etwas verändert. Weitere Einzelheiten zum Entfernen von .NET Core-Versionen, die nicht mehr benötigt werden, finden Sie unter [Entfernen der .NET Core-Runtime und des SDK](remove-runtime-sdk-versions.md) in der [Dokumentation zu .NET Core](../index.md).
