---
title: Konfigurieren kryptografischer Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: b5c1178519601d7dcb7c5b3014f413b6436746fb
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816170"
---
# <a name="configuring-cryptography-classes"></a>Konfigurieren kryptografischer Klassen
Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Computeradministratoren so konfigurieren Sie die standardmäßigen kryptoalgorithmen und algorithmusimplementierungen, die .NET Framework und entsprechend geschriebene Anwendungen verwenden, können.  Beispielsweise kann eine Organisation, die eine eigene Implementierung des ein kryptografischer Algorithmus verfügt, diese Implementierung die Standardeinstellung anstelle der Implementierung versendet im Windows SDK. Obwohl es sich bei verwaltete Anwendungen, mit denen Kryptografie immer explizit an eine bestimmte Implementierung gebunden auswählen können, empfiehlt es sich, dass sie kryptografische Objekte mithilfe von kryptografischen Konfigurationssystem erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von Algorithmennamen zu kryptografischen Klassen](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Beschreibt, wie ein Algorithmusnamens zu einer kryptografischen Klasse zuordnen.  
  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Beschreibt, wie eine Objekt-ID zu einem kryptografischen Algorithmus zuordnen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Bietet eine Übersicht über kryptografische Dienste, die vom Windows SDK bereitgestellt werden.  
  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.
