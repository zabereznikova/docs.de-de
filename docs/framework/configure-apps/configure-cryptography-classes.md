---
title: Konfigurieren kryptografischer Klassen
description: Erfahren Sie, wie Computer Administratoren die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen konfigurieren können, die von .net und Anwendungen verwendet werden.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5262dfca914fd5306297ea9535bcef3d2088d107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165207"
---
# <a name="configuring-cryptography-classes"></a>Konfigurieren kryptografischer Klassen

Der Windows SDK ermöglicht es Computer Administratoren, die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen zu konfigurieren, die von den .NET Framework und entsprechend geschriebenen Anwendungen verwendet werden.  Beispielsweise kann ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus verfügt, diese Implementierung als Standardwert anstelle der in der Windows SDK gelieferten Implementierung festlegen. Obwohl verwaltete Anwendungen, die Kryptografie verwenden, immer eine explizite Bindung an eine bestimmte Implementierung treffen können, empfiehlt es sich, kryptografieobjekte mithilfe des kryptografiekonfigurationssystems zu erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Zuordnen von Algorithmennamen zu kryptografischen Klassen](map-algorithm-names-to-cryptography-classes.md)  
 Beschreibt, wie ein Algorithmusname einer Kryptografieklasse zugeordnet wird.  
  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](map-object-identifiers-to-cryptography-algorithms.md)  
 Beschreibt, wie ein Objekt Bezeichner einem Kryptografiealgorithmus zugeordnet wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Kryptografische Dienste](../../standard/security/cryptographic-services.md)  
 Bietet eine Übersicht über die Kryptografiedienste, die von der Windows SDK bereitgestellt werden.  
  
 [Schema für Kryptografieeinstellungen](./file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.
