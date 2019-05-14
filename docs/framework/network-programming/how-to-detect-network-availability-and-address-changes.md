---
title: 'Vorgehensweise: Erkennen von Netzwerkverfügbarkeit und Adressänderungen'
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
ms.openlocfilehash: 8066286f458c730671acbafd713d0cbda4218ec3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624620"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="e4a31-102">Vorgehensweise: Erkennen von Netzwerkverfügbarkeit und Adressänderungen</span><span class="sxs-lookup"><span data-stu-id="e4a31-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="e4a31-103">In diesem Beispiel wird gezeigt, wie Änderungen in der Netzwerkadresse einer Schnittstelle erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="e4a31-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a31-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4a31-104">Example</span></span>  
  
```  
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new   
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4a31-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e4a31-105">Compiling the Code</span></span>  
 <span data-ttu-id="e4a31-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e4a31-106">This example requires:</span></span>  
  
- <span data-ttu-id="e4a31-107">Verweise auf den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="e4a31-107">References to the **System.Net** namespace.</span></span>
