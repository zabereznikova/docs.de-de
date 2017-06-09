---
title: "Konfigurieren kryptografischer Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework-Anwendungskonfiguration, Kryptografie"
  - "Konfigurationsdateien [.NET Framework], Kryptografie"
  - "Kryptografische Algorithmen"
  - "Kryptografie, Klassen"
  - "Standardkryptografie"
  - "Sicherheit [.NET Framework], Verschlüsselung"
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Konfigurieren kryptografischer Klassen
Mit [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] können Computeradministratoren die Standard\-Kryptografiealgorithmen und Algorithmusimplementierungen konfigurieren, die das .NET Framework und entsprechend geschriebene Anwendungen verwenden.  Beispielsweise kann eine Organisation, die über eine eigene Implementierung eines Kryptografiealgorithmus verfügt, diese Implementierung anstelle der in [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)] enthaltenen Implementierung zum Standard erklären.  Obwohl sich verwaltete Anwendungen, die Kryptografie verwenden, immer explizit an eine bestimmte Implementierung binden können, wird empfohlen, das Erstellen von kryptografischen Objekten über das Kryptokonfigurationssystem ausführen zu lassen.  
  
## In diesem Abschnitt  
 [Zuordnen von Algorithmennamen zu kryptografischen Klassen](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Beschreibt das Zuordnen eines Algorithmusnamens zu einer kryptografischen Klasse.  
  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Beschreibt das Zuordnen eines Objektbezeichners zu einem kryptografischen Algorithmus.  
  
## Verwandte Abschnitte  
 [Kryptografische Dienste](../../../docs/standard/security/cryptographic-services.md)  
 Bietet eine Übersicht über kryptografische Dienste von [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Schema für Kryptografieeinstellungen](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.