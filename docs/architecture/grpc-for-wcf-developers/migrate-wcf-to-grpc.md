---
title: Migrieren einer WCF-Lösung zu GrpC-GrpC für WCF-Entwickler
description: Vorgehensweise beim Migrieren verschiedener Typen von WCF-Diensten zu den entsprechenden Typen in GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: 12e724ab46a33547d352da7a604a5a994e617bc2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628513"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Migrieren einer WCF-Lösung zu gRPC

In diesem Kapitel wird beschrieben, wie Sie mit ASP.net Core 3,0-GrpC-Projekten arbeiten und die Migration verschiedener Typen von Windows Communication Foundation (WCF)-Diensten zu der GrpC-Entsprechung veranschaulichen:

- Erstellen Sie ein ASP.net Core 3,0-GrpC-Projekt.
- Einfache Anforderung/Antwort-Vorgänge an den unären GrpC-RPC.
- Unidirektionale Vorgänge zum GrpC-clientstreaming von RPC.
- Vollduplex Dienste für das bidirektionale Streaming von GrpC.

Es gibt auch einen Vergleich der Verwendung von Streamingdiensten im Vergleich zu wiederholten Feldern für die Rückgabe von Datasets, und es gibt eine Erörterung der Verwendung von Client Bibliotheken am Ende des Kapitels.

Bei der WCF-Beispielanwendung handelt es sich um einen minimalen Stub für eine Reihe von Aktienhandels Diensten. Er verwendet die Open Source-Container Bibliothek "Inversion of Control (IOC)" mit dem Namen "autofac" für die Abhängigkeitsinjektion. Sie enthält drei Dienste, eine für jeden WCF-Diensttyp. Die Dienste werden in den folgenden Abschnitten ausführlicher erläutert. Sie können die Lösungen von [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) auf GitHub herunterladen. Die Dienste verwenden gefälschte Daten, um externe Abhängigkeiten zu minimieren.

Die Beispiele umfassen die WCF-und GrpC-Implementierungen der einzelnen Dienste.

>[!div class="step-by-step"]
>[Zurück](ws-protocols.md)
>[Weiter](create-project.md)
