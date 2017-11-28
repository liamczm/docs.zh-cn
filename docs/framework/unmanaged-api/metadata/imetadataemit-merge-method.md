---
title: "IMetaDataEmit::Merge 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Merge
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42ebc188dfecde068ef8e2979970118fee91ec4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="a919c-102">IMetaDataEmit::Merge 方法</span><span class="sxs-lookup"><span data-stu-id="a919c-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="a919c-103">将指定的导入作用域添加到要合并的范围列表。</span><span class="sxs-lookup"><span data-stu-id="a919c-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a919c-104">语法</span><span class="sxs-lookup"><span data-stu-id="a919c-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a919c-105">参数</span><span class="sxs-lookup"><span data-stu-id="a919c-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="a919c-106">[in]指向的指针[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)标识要合并的导入的作用域的对象。</span><span class="sxs-lookup"><span data-stu-id="a919c-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="a919c-107">[in]指向的指针[IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)对象，它指定令牌重新映射。</span><span class="sxs-lookup"><span data-stu-id="a919c-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="a919c-108">[in]指向的指针<!--<<!--zzxref:IUnknown --> `IUnknown` >-->  `IUnknown`对象，它指定了错误。</span><span class="sxs-lookup"><span data-stu-id="a919c-108">[in] A pointer to an <!--<<!--zzxref:IUnknown --> `IUnknown`>--> `IUnknown` object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a919c-109">备注</span><span class="sxs-lookup"><span data-stu-id="a919c-109">Remarks</span></span>  
 <span data-ttu-id="a919c-110">调用[imetadataemit:: Mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)触发的元数据合并到单个作用域。</span><span class="sxs-lookup"><span data-stu-id="a919c-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a919c-111">要求</span><span class="sxs-lookup"><span data-stu-id="a919c-111">Requirements</span></span>  
 <span data-ttu-id="a919c-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a919c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a919c-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a919c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a919c-114">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a919c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a919c-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a919c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a919c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a919c-116">See Also</span></span>  
 [<span data-ttu-id="a919c-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a919c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a919c-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="a919c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)