---
title: Für WCF erforderliche Betriebssystemressourcen
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961133"
---
# <a name="operating-system-resources-required-by-wcf"></a>Für WCF erforderliche Betriebssystemressourcen

Windows Communication Foundation (WCF) hängt von mehreren Ressourcen ab, die vom Betriebssystem zur Funktionsweise bereitgestellt werden. In der folgenden Tabelle sind diese Ressourcen aufgeführt:

|Ressource|Beschreibung|
|--------------|-----------------|
|Microsoft Distributed Transaction Coordinator (MSDTC)|Zur Unterstützung von OleTx-Transaktionen erforderlich.|
|IIS (Internet Information Services)|Erforderlich, wenn Sie IIS zum Hosten der Anwendung verwenden möchten.|
|Windows Process Activation Service (WAS)|Erforderlich, wenn Sie WAS zum Hosten der Anwendung verwenden möchten.|
