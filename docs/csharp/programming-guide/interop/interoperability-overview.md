---
title: "Überblick über die Interoperabilität (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b24a367eaf78ef520cc2dd54db6ad58b215179ad
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="interoperability-overview-c-programming-guide"></a>Überblick über die Interoperabilität (C#-Programmierhandbuch)
Dieses Thema beschreibt Methoden zur Gewährleistung der Interoperabilität zwischen von C#-verwaltetem und nicht verwaltetem Code.  
  
## <a name="platform-invoke"></a>Plattformaufruf  
 Der *Plattformaufruf* ist ein Dienst, der es verwaltetem Code ermöglicht, nicht verwaltete Funktionen aufzurufen, die in DLLs (Dynamic Link Library) implementiert sind, z.B. die in der Microsoft Win32-API enthaltenen Funktionen. Es sucht eine exportierte Funktion, ruft diese auf und marshallt ihre Argumente (ganze Zahlen, Zeichenfolgen, Arrays, Strukturen usw.) bei Bedarf über die Grenzen des dialogfähigen Betriebs hinaus.  
  
 Weitere Informationen finden Sie unter [Verwenden nicht verwalteter DLL-Funktionen](../../../framework/interop/consuming-unmanaged-dll-functions.md) und [Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).  
  
> [!NOTE]
>  Die [Common Language Runtime](../../../standard/clr.md) (CLR) verwaltet den Zugriff auf Systemressourcen. Das Aufrufen von nicht verwaltetem Code, der sich außerhalb der CLR befindet, umgeht diesen Sicherheitsmechanismus; deshalb stellt er ein Sicherheitsrisiko dar. Nicht verwalteter Code kann z.B. Ressourcen in nicht verwaltetem Code direkt aufrufen und umgeht damit die Sicherheitsmechanismen der CLR. Weitere Informationen finden Sie unter [.NET Framework-Sicherheit](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## <a name="c-interop"></a>C++ Interop  
 Sie können C++ Interop – auch als It Just Works (IJW) bezeichnet – verwenden, um ein native C++-Klasse zu umschließen, sodass diese von in C# oder in einer anderen .NET Framework-Programmiersprache geschriebenem Code genutzt werden kann. Dafür schreiben Sie C++-Code, der eine native DLL- oder COM-Komponente umschließen kann. Im Gegensatz zu anderen .NET-Programmiersprachen verfügt [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] über eine Interoperabilitätsunterstützung, dank der verwalteter und nicht verwalteter Code in derselben Anwendung und sogar in derselben Datei verwendet werden können. Anschließend erstellen Sie den C++-Code mithilfe des **/clr**-Compilerschalters, um eine verwaltete Assembly zu erzeugen. Zuletzt fügen Sie der Assembly in Ihrem C#-Projekt einen Verweis hinzu und verwenden das umschlossene Objekt genauso wie eine andere verwaltete Klasse.  
  
## <a name="exposing-com-components-to-c"></a>Verfügbarmachen von COM-Komponenten in C#  
 Sie können eine COM-Komponente aus einem C#-Projekt nutzen. Dies sind die Hauptschritte:  
  
1.  Suchen Sie eine COM-Komponenten, die Sie verwenden möchten, und registrieren Sie diese. Verwenden Sie „regsvr32.exe“ zur Registrierung und Aufhebung der Registrierung einer COM-DLL.  
  
2.  Fügen Sie dem Projekt einen Verweis auf eine COM-Komponente oder eine Typbibliothek hinzu.  
  
     Beim Hinzufügen des Verweises verwendet [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] das [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382), das eine Typbibliothek als Eingabe akzeptiert, um eine .NET Framework-Interopassembly auszugeben. Die Assembly – auch als Runtime Callable Wrapper (RCW) bezeichnet – enthält verwaltete Klassen und Schnittstellen, die die COM-Klassen und -Schnittstellen umschließen, die sich in der Typbibliothek befinden. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] fügt dem Projekt einen Verweis auf die generierte Assembly hinzu.  
  
3.  Erstellen Sie eine Instanz einer im RCW definierten Klasse. Dadurch wird wiederum eine Instanz des COM-Objekts erstellt.  
  
4.  Verwenden Sie das Objekt genauso, wie Sie andere verwaltete Objekte verwenden. Wenn das Objekt von der automatische Speicherbereinigung freigegeben wird, wird auch die Instanz des COM-Objekts aus dem Speicher freigestellt.  
  
 Weitere Informationen finden Sie unter [Verfügbarmachen von COM-Komponenten für .NET Framework](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730).  
  
## <a name="exposing-c-to-com"></a>Verfügbarmachen von C# für COM  
 COM-Clients können C#-Typen nutzen, die ordnungsgemäß verfügbar gemacht wurden. Dies sind die grundlegenden Schritte für das Verfügbarmachen von C#-Typen:  
  
1.  Fügen Sie Ihrem C#-Projekt Interop-Attribute hinzu.  
  
     Durch das Modifizieren der [!INCLUDE[csprcs](~/includes/csprcs-md.md)]-Projekteinstellungen können Sie eine Assembly COM-sichtbar machen. Weitere Informationen finden Sie unter [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box).  
  
2.  Generieren Sie eine COM-Typbibliothek, und registrieren Sie diese für den Gebrauch mit COM.  
  
     Sie können die [!INCLUDE[csprcs](~/includes/csprcs-md.md)]-Projekteinstellungen so modifizieren, dass die C#-Assembly automatisch für COM-Interop registriert wird. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] verwendet das [Regasm.exe (Assembly Registration-Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb) mithilfe des Befehlszeilenschalters `/tlb`, das die verwaltete Assembly als Eingabe akzeptiert, um eine Typbibliothek zu generieren. Diese Typbibliothek beschreibt den Typ `public` in der Assembly und fügt Verzeichniseinträge hinzu, um COM-Clients das Erstellen verwalteter Klassen zu ermöglichen.  
  
 Weitere Informationen finden Sie unter [Verfügbarmachen von .NET Framework-Komponenten in COM](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6) und [COM-Beispielklasse](../../../csharp/programming-guide/interop/example-com-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Improving Interop Performance (Optimieren der Interopleistung)](http://go.microsoft.com/fwlink/?LinkId=99564)  
 [Einführung in COM-Interop](http://go.microsoft.com/fwlink/?LinkId=112406)  
 [Marshaling between Managed and Unmanaged Code (Marshalling zwischen verwaltetem und nicht verwaltetem Code)](http://go.microsoft.com/fwlink/?LinkId=112398)  
 [Interoperabilität mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md)  
 [Erweiterte COM-Interoperabilität](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
