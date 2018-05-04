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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configuring-cryptography-classes"></a>Konfigurieren kryptografischer Klassen
Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Computeradministratoren so konfigurieren Sie die standardmäßige kryptografische Algorithmen und Algorithmus-Implementierungen, die .NET Framework und entsprechend geschriebene Anwendungen verwenden können.  Beispielsweise ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus kann als, dass diese Implementierung standardanwendung anstelle der Implementierung, die im Lieferumfang der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Zwar verwaltete Anwendungen, die Kryptografie verwenden immer auswählen können, um explizit an eine bestimmte Implementierung zu binden, wird empfohlen, sie kryptografische Objekte mithilfe der CryptoAPI Konfigurationssystem erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von Algorithmennamen zu kryptografischen Klassen](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Beschreibt das Zuordnen ein Algorithmusnamens zu einer kryptografischen Klasse.  
  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Beschreibt, wie der Bezeichner eines Objekts zu einem kryptografischen Algorithmus zuordnen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Bietet eine Übersicht über kryptografische Dienste von der [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.
