---
title: "Foreground and Background Threads | Microsoft Docs"
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
  - "threading [.NET Framework], foreground"
  - "threading [.NET Framework], background"
  - "foreground threads"
  - "background threads"
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Foreground and Background Threads
Ein verwalteter Thread ist entweder ein Hintergrund\- oder Vordergrundthread.  Hintergrund\- und Vordergrundthreads sind bis auf eine Ausnahme gleich: Durch einen Hintergrundthread wird die verwaltete Ausführungsumgebung nicht aufrecht erhalten.  Sobald alle Vordergrundthreads in einem verwalteten Prozess \(in dem die EXE\-Datei eine verwaltete Assembly ist\) gestoppt wurden, stoppt das System alle Hintergrundthreads und schaltet sich ab.  
  
> [!NOTE]
>  Wenn ein Hintergrundthread von der Laufzeit angehalten wird, da der Prozess beendet wird, wird keine Ausnahme im Thread ausgelöst.  Wenn Threads jedoch angehalten werden, weil die Anwendungsdomäne von der <xref:System.AppDomain.Unload%2A?displayProperty=fullName>\-Methode entladen wird, wird sowohl in Vordergrund\- als auch in Hintergrundthreads eine <xref:System.Threading.ThreadAbortException>\-Ausnahme ausgelöst.  
  
 Verwenden Sie die <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName>\-Eigenschaft, um festzustellen, ob es sich bei dem Thread um einen Hintergrund\- oder Vordergrundthread handelt, oder um dessen Status zu ändern.  Ein Thread kann jederzeit in einen Hintergrundthread geändert werden, indem seine <xref:System.Threading.Thread.IsBackground%2A>\-Eigenschaft auf `true` festgelegt wird.  
  
> [!IMPORTANT]
>  Der Vorder\- oder Hintergrundstatus eines Threads hat keinen Einfluss auf das Ergebnis einer unbehandelten Ausnahme im Thread.  In .NET Framework, Version 2.0, führt eine unbehandelte Ausnahme in Vorder\- und Hintergrundthreads dazu, dass die Anwendung beendet wird.  Siehe [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Bei Threads aus dem verwalteten Threadpool \(Threads, deren <xref:System.Threading.Thread.IsThreadPoolThread%2A>\-Eigenschaft auf `true` festgelegt ist\) handelt es sich um Hintergrundthreads.  Alle Threads, die von nicht verwaltetem Code in die verwaltete Ausführungsumgebung gelangen, werden als Hintergrundthreads markiert.  Alle Threads, die durch Erstellen und Starten eines neuen <xref:System.Threading.Thread>\-Objekts generiert wurden, sind standardmäßig Vordergrundthreads.  
  
 Wenn Sie einen Thread zur Überwachung einer Aktivität, z. B. einer Socketverbindung, verwenden, legen Sie seine <xref:System.Threading.Thread.IsBackground%2A>\-Eigenschaft auf `true` fest, damit die Beendigung des Prozesses nicht durch den Thread verhindert wird.  
  
## Siehe auch  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName>   
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadAbortException>