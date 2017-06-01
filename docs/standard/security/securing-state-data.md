---
title: "Securing State Data | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], state data"
  - "code security, state data"
  - "secure coding, state data"
  - "state data security"
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Securing State Data
Anwendungen, die vertrauliche Daten verarbeiten und Sicherheitsentscheidungen treffen, müssen diese Daten unter eigener Kontrolle behalten und sie vor dem direkten Zugriff durch möglicherweise böswilligen Code schützen.  Die beste Möglichkeit für den Schutz der Daten im Speicher besteht darin, diese als private bzw. interne \(Gültigkeitsbereich auf dieselbe Assembly beschränkt\) Variablen zu deklarieren.  Sie müssen sich jedoch darüber im Klaren sein, dass auch dann auf die Daten zugegriffen wird:  
  
-   Sehr vertrauenswürdiger Code, der auf das Objekt verweisen kann, kann anhand von Reflektion private Member abrufen und festlegen.  
  
-   Sehr vertrauenswürdiger Code kann private Member mithilfe von Serialisierung abrufen und festlegen, wenn er auf die entsprechenden Daten des Objekts in serialisierter Form zugreifen kann.  
  
-   Beim Debuggen können diese Daten gelesen werden.  
  
 Stellen Sie sicher, dass diese Werte nicht versehentlich durch Ihre eigenen Methoden und Eigenschaften verfügbar gemacht werden.  
  
 In einigen Fällen können Daten als "protected" deklariert werden, wobei der Zugriff auf die Klasse und ihre Ableitungen beschränkt ist.  Aufgrund einer weiteren Gefährdung sollten Sie die folgenden zusätzlichen Sicherheitsvorkehrungen treffen:  
  
-   Legen Sie fest, welcher Code von der Klasse ableiten darf, indem Sie diesen auf dieselbe Assembly beschränken oder indem Sie mithilfe von deklarativer Sicherheit eine bestimmte Identität oder bestimmte Berechtigungen fordern \(siehe unter [Sichern des Methodenzugriffs](../../../docs/framework/misc/securing-method-access.md)\).  
  
-   Achten Sie darauf, dass für alle abgeleiteten Klassen ein vergleichbarer Schutz implementiert ist oder diese versiegelt werden.  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)