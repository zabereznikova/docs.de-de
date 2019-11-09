---
title: Migrieren einer WCF-Lösung zu GrpC-GrpC für WCF-Entwickler
description: Vorgehensweise beim Migrieren verschiedener Typen von WCF-Diensten zu den entsprechenden Typen in GrpC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 65c30b777d9981cb3291b846f698f2a69b4498fc
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841498"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Migrieren einer WCF-Lösung zu gRPC

In diesem Kapitel wird erläutert, wie Sie mit ASP.net Core 3,0-GrpC-Projekten arbeiten und die Migration verschiedener WCF-Dienst Typen auf die entsprechende GrpC-Entsprechung veranschaulichen:

- Erstellen Sie ein ASP.net Core 3,0-GrpC-Projekt.
- Einfache Anforderung/Antwort-Vorgänge an den unären GrpC-RPC.
- Unidirektionale Vorgänge zum GrpC-clientstreaming von RPC.
- Vollständige Duplex Dienste für das bidirektionale Streaming von GrpC.

Es gibt auch einen Vergleich der Verwendung von Streamingdiensten im Vergleich zu wiederholten Feldern für die Rückgabe von Datasets und die Verwendung von Client Bibliotheken am Ende des Kapitels.

Bei der WCF-Beispielanwendung handelt es sich um einen minimalen Stub für eine Reihe von Aktienhandels Diensten, die die Open Source-IoC-Container Bibliothek (Inversion of Control) mit dem Namen *autofac* für die Abhängigkeitsinjektion verwenden. Sie enthält drei Dienste, eine für jeden WCF-Diensttyp. Die Dienste werden in den folgenden Abschnitten ausführlicher erläutert. Die Lösungen können von [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) auf GitHub heruntergeladen werden. Die Dienste verwenden gefälschte Daten, um externe Abhängigkeiten zu minimieren.

Die Beispiele umfassen die WCF-und GrpC-Implementierungen der einzelnen Dienste.

>[!div class="step-by-step"]
>[Zurück](ws-protocols.md)
>[Weiter](create-project.md)
