---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 9235f1bcda7529b71aef542d3a49da08a9d4b59e
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590589"
---
Unsichere deserialisierungssoren sind beim Deserialisieren nicht vertrauenswürdiger Daten anfällig. Ein Angreifer könnte die serialisierten Daten so ändern, dass unerwartete Typen eingefügt werden, um Objekte mit bösartigen Nebeneffekten einzuschleusen. Ein Angriff auf ein unsicherer Deserialisierungsprogramm könnte z. b. Befehle für das zugrunde liegende Betriebssystem ausführen, über das Netzwerk kommunizieren oder Dateien löschen.
