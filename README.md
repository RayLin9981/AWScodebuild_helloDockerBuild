# 基礎 AWS CICD Pipeline 測試

source (github) -> build (AWS codeBuild) -> deploy (AWS ECS)  

## AWS codeBuild 部分
很簡單的測試，透過修改 index.html 然後 build images 來觀察變化    
目前 docker hub 會有 pull 的流量限制 (在 AWS 上基本無法使用)，因此我把 image 放在 `quay.io` 上 ( `quay.io/raylin9981` )  
CodeBuild 需要丟出一個 Artifacts 供 CodePipeline 使用 (`imagedefinitions.json`) (應該說是給 AWS ECS 使用) 
