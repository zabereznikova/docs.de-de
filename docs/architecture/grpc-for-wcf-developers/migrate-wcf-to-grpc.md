---
title: Migrieren einer WCF-Lösung zu GrpC-GrpC für WCF-Entwickler
description: Vorgehensweise beim Migrieren verschiedener Typen von WCF-Diensten zu den entsprechenden Typen in GrpC.
ms.date: 12/15/2020
ms.openlocfilehash: 3bd35cb6119368ff3db3be9ab5fabf89f2652b29
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97937960"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Migrieren einer WCF-Lösung zu gRPC

In diesem Kapitel wird beschrieben, wie Sie mit ASP.net Core 5,0-GrpC-Projekten arbeiten und die Migration verschiedener Typen von Windows Communication Foundation (WCF)-Diensten zu der GrpC-Entsprechung veranschaulichen:

- Erstellen Sie ein ASP.net Core 5,0-GrpC-Projekt.
- Einfache Anforderung/Antwort-Vorgänge an den unären GrpC-RPC.
- Unidirektionale Vorgänge zum GrpC-clientstreaming von RPC.
- Vollduplex Dienste für das bidirektionale Streaming von GrpC.

Es gibt auch einen Vergleich der Verwendung von Streamingdiensten im Vergleich zu wiederholten Feldern für die Rückgabe von Datasets, und es gibt eine Erörterung der Verwendung von Client Bibliotheken am Ende des Kapitels.

Bei der WCF-Beispielanwendung handelt es sich um einen minimalen Stub für eine Reihe von Aktienhandels Diensten. Er verwendet die Open Source-Container Bibliothek "Inversion of Control (IOC)" mit dem Namen "autofac" für die Abhängigkeitsinjektion. Sie enthält drei Dienste, eine für jeden WCF-Diensttyp. Die Dienste werden in den folgenden Abschnitten ausführlicher erläutert. Sie können die Lösungen von [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) auf GitHub herunterladen. Die Dienste verwenden gefälschte Daten, um externe Abhängigkeiten zu minimieren.

Die Beispiele umfassen die WCF-und GrpC-Implementierungen der einzelnen Dienste.

>[!div class="step-by-step"]
>[Zurück](ws-protocols.md)
>[Weiter](create-project.md)
