---
title: Microsoft.AspNetCore.All metapackage para ASP.NET Core 2.x y versiones posteriores
author: Rick-Anderson
description: El metapackage Microsoft.AspNetCore.All incluye todos los paquetes de ASP.NET Core y Entity Framework Core, junto con sus dependencias.
keywords: Core,NuGet,package,Microsoft.AspNetCore.All,metapackage de ASP.NET
ms.author: riande
manager: wpickett
ms.date: 09/20/2017
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: fundamentals/metapackage
ms.openlocfilehash: ff25d80be907994f7ac3d64a8ffa39ae53278ba6
ms.sourcegitcommit: 73bf6b222474d9f1f6aba3feaca4e191069d2121
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2017
---
#<a name="microsoftaspnetcoreall-metapackage-for-aspnet-core-2x"></a>Microsoft.AspNetCore.All metapackage para ASP.NET Core 2.x

Esta característica requiere ASP.NET Core 2.x destinatarios .NET Core 2.x.

El metapaquete [Microsoft.AspNetCore.All](https://www.nuget.org/packages/Microsoft.AspNetCore.All) para ASP.NET Core incluye lo siguiente:

* Todos los paquetes admitidos por el equipo de ASP.NET Core.
* Todos los paquetes admitidos por Entity Framework Core. 
* Dependencias internas y de terceros usadas por ASP.NET Core y Entity Framework Core. 

Todas las características de ASP.NET Core 2.x y Entity Framework Core 2.x se incluyen en el `Microsoft.AspNetCore.All` paquete. Las plantillas de proyecto predeterminadas usan este paquete.

El número de versión de la `Microsoft.AspNetCore.All` metapackage representa la versión de ASP.NET Core y la versión de Entity Framework Core (alineado con la versión de .NET Core).

Las aplicaciones que utilizan el `Microsoft.AspNetCore.All` metapackage automáticamente aprovechar la [almacén de tiempo de ejecución de .NET Core](https://docs.microsoft.com/dotnet/core/deploying/runtime-store). El almacén de tiempo de ejecución contiene todos los activos en tiempo de ejecución necesarios para ejecutar ASP.NET Core aplicaciones 2.x. Cuando se usa el `Microsoft.AspNetCore.All` metapackage, **no** activos de los paquetes de NuGet de núcleo de ASP.NET que se hace referencia se implementan con la aplicación &mdash; el almacén de tiempo de ejecución de .NET Core contiene estos activos. Los activos en el almacén de tiempo de ejecución se precompilan para mejorar el tiempo de inicio de la aplicación.

Puede usar el proceso de recorte de paquete para quitar los paquetes que no se usan. Se excluyen recortados paquetes de salida de la aplicación publicada.

El siguiente *.csproj* referencias de archivo la `Microsoft.AspNetCore.All` metapackage principales de ASP.NET:

[!code-xml[Main](..\mvc\views\view-compilation\sample\MvcRazorCompileOnPublish2.csproj?highlight=9)]
