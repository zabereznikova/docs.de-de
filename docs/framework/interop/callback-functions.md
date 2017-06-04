---
title: "Callback Functions | Microsoft Docs"
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
  - "callback function"
  - "platform invoke, calling unmanaged functions"
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Callback Functions
Eine Rückruffunktion ist Code innerhalb einer verwalteten Anwendung, der eine nicht verwaltete DLL\-Funktion bei der Durchführung ihrer Aufgabe unterstützt.  Aufrufe an eine Rückruffunktion werden indirekt von einer verwalteten Anwendung übergeben, und zwar über eine DLL\-Funktion, und gelangen wieder zurück zur verwalteten Implementierung.  Von den vielen DLL\-Funktionen, die mit Plattformaufruf aufgerufen werden, benötigen einige eine Rückruffunktion in verwaltetem Code, damit sie ordnungsgemäß ausgeführt werden können.  
  
 Die meisten DLL\-Funktionen können in verwaltetem Code aufgerufen werden, indem eine verwaltete Definition der Funktion erstellt und diese anschließend aufgerufen wird.  Dies ist ein ganz einfacher Vorgang.  
  
 Wenn Sie eine DLL\-Funktion verwenden, für die eine Rückruffunktion erforderlich ist, müssen Sie einige zusätzliche Schritte ausführen.  Ermitteln Sie zunächst anhand der Dokumentation für die Funktion, ob ein Rückruf erforderlich ist.  Anschließend müssen Sie die Rückruffunktion in der verwalteten Anwendung erstellen.  Schließlich können Sie die DLL\-Funktion aufrufen, indem Sie der Rückruffunktion einen Zeiger als Argument übergeben.  In der folgenden Abbildung werden diese Schritte zusammengefasst.  
  
 ![Rückruf für Plattformaufruf](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
Rückruffunktion und Implementierung  
  
 Rückruffunktionen eignen sich besonders in Situationen, in denen eine Aufgabe wiederholt durchgeführt wird.  Häufig werden sie auch mit Enumerationsfunktionen verwendet, z. B. **EnumFontFamilies**, **EnumPrinters** und **EnumWindows** in der Win32\-API.  Mit der **EnumWindows**\-Funktion werden alle vorhandenen Fenster des Computers aufgelistet, und die Rückruffunktion wird zum Durchführen einer Aufgabe für alle Fenster aufgerufen.  Anweisungen und ein Beispiel finden Sie unter [Gewusst wie: Implementieren von Rückruffunktionen](../../../docs/framework/interop/how-to-implement-callback-functions.md).  
  
## Siehe auch  
 [How to: Implement Callback Functions](../../../docs/framework/interop/how-to-implement-callback-functions.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)