---
title: "Exposing .NET Framework Components to COM | Microsoft Docs"
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
  - "exposing .NET Framework components to COM"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Exposing .NET Framework Components to COM
Das Schreiben eines .NET\-Typs stellt für einen Entwickler eine andere Aktivität dar als das Verarbeiten dieses Typs aus nicht verwaltetem Code.  In diesem Abschnitt werden einige Tipps zum Schreiben von verwaltetem Code gegeben, der mit COM\-Clients zusammenwirkt:  
  
-   [Qualifizieren von .NET\-Typen für die Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
     Alle verwalteten Typen, Methoden, Eigenschaften, Felder und Ereignisse, die für COM verfügbar gemacht werden sollen, müssen öffentlich sein.  Typen müssen über einen öffentlichen Standardkonstruktor verfügen, da dies der einzige Konstruktor ist, der über COM aufgerufen werden kann.  
  
-   [Anwenden von Interop\-Attributen](../../../docs/framework/interop/applying-interop-attributes.md).  
  
     Benutzerdefinierte Attribute in verwaltetem Code können die Interoperabilität einer Komponente verbessern.  
  
-   [Verpacken einer Assembly für COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).  
  
     COM\-Entwickler benötigen gegebenenfalls eine Zusammenfassung der Schritte zum Referenzieren und Bereitstellen von Assemblys.  
  
 Darüber hinaus werden in diesem Abschnitt die Aufgaben benannt, die in Zusammenhang mit der Beanspruchung eines verwalteten Typs durch einen COM\-Client stehen.  
  
#### So verarbeiten Sie einen verwalteten Typ von COM  
  
1.  [Registrieren Sie Assemblys mit COM](../../../docs/framework/interop/registering-assemblies-with-com.md).  
  
     Typen in einer Assembly \(und Typbibliotheken\) müssen zum Zeitpunkt des Entwurfs registriert werden.  Wenn die Assembly nicht von einem Installer registriert wird, müssen COM\-Entwickler angewiesen werden, **Regasm.exe** ausführen.  
  
2.  [Verweisen Sie auf .NET\-Typen in COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).  
  
     Zum Verweisen auf die Typen in einer Assembly können COM\-Entwickler die bekannten Techniken und Tools verwenden.  
  
3.  [Rufen Sie ein .NET\-Objekt auf](http://msdn.microsoft.com/de-de/40c9626c-aea6-4bad-b8f0-c1de462efd33).  
  
     COM\-Entwickler können Methoden für .NET\-Objekte in gleicher Weise aufrufen wie Methoden für nicht verwaltete Typen.  Die **CoCreateInstance**\-COM\-API z. B. aktiviert .NET\-Objekte.  
  
4.  [Geben Sie eine Anwendung für COM\-Zugriff weiter](http://msdn.microsoft.com/de-de/fb63564c-c1b9-4655-a094-a235625882ce).  
  
     Eine Assembly mit starkem Namen kann im globalen Assemblycache installiert werden. Sie bedarf einer Signatur vom Herausgeber.  Assemblys ohne starke Namen müssen im Anwendungsverzeichnis des Clients installiert werden.  
  
## Siehe auch  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)   
 [COM Interop Sample: COM Client and .NET Server](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)