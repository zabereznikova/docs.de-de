---
title: "How to: Prevent a Child Task from Attaching to its Parent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, preventing attachments"
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Prevent a Child Task from Attaching to its Parent
Dieses Dokument veranschaulicht, wie eine untergeordnete Aufgabe am Anfügen zur übergeordneten Aufgabe verhindert.  Eine untergeordnete Aufgabe am Anfügen an übergeordnete zu verhindern ist hilfreich, wenn Sie eine Komponente aufrufen, die von einem Drittanbieter geschrieben wird und die außerdem Aufgaben verwendet.  Beispielsweise kann eine Komponente von Drittanbietern, die die <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> \- Option verwendet, ein <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>\-Objekt, Probleme im Code verursachen, wenn sie mit langer Laufzeit ist oder eine Ausnahme auslöst.  
  
## Beispiel  
 Im folgenden Beispiel werden die Auswirkungen der Verwendung der Standardoptionen zu den Auswirkungen Verhindern einer untergeordneten Aufgabe am Anfügen übergeordnete Element.  Im Beispiel wird ein <xref:System.Threading.Tasks.Task>\-Objekt, das in eine Bibliothek eines Drittanbieters aufruft, die auch ein <xref:System.Threading.Tasks.Task>\-Objekt verwendet.  Die Bibliothek von Drittanbietern verwendet die <xref:System.Threading.Tasks.TaskCreationOptions> \- Option, das <xref:System.Threading.Tasks.Task>\-Objekt zu erstellen.  Die Anwendung verwendet die <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> \- Option, die übergeordnete Aufgabe zu erstellen.  Diese Option weist die Laufzeit an, die <xref:System.Threading.Tasks.TaskCreationOptions> Spezifikation in den untergeordneten Aufgaben zu entfernen.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Da eine übergeordnete Aufgabe nicht beendet, bis alle untergeordneten Aufgaben beendet, kann eine untergeordnete Aufgabe mit langer Laufzeit der Gesamtanwendung verursachen, fehlerhaft auszuführen.  In diesem Beispiel die Anwendung die Standardoptionen verwendet, die übergeordnete Aufgabe zu erstellen, muss auch die untergeordnete Aufgabe beenden, bevor die übergeordnete Aufgabe beendet.  Wenn die Anwendung die <xref:System.Threading.Tasks.TaskCreationOptions?displayProperty=fullName> \- Option verwenden, wird das untergeordnete Element nicht in den übergeordneten Element angefügt.  Daher kann die Anwendung weitere Arbeit ausführen nach dem Ende der übergeordneten Aufgabe und bevor sie auf die untergeordnete Aufgabe warten muss zu beenden.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `DenyChildAttach.cs` \(`DenyChildAttach.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## Robuste Programmierung  
  
## Siehe auch  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)