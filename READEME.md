# ArgoCD

## 개념

## 설치 및 사용

### 배포

```
# Helm 저장소 추가
helm repo add argo https://argoproj.github.io/argo-helm

# Helm 저장소 업데이트
helm repo update

# 네임스페이스 생성 (이미 존재한다면 생략 가능)
kubectl create namespace argocd

# Helm 차트 설치
helm install argo-cd argo/argo-cd -f values.yaml -n argocd
```

### ingress 적용

```
k apply -f ingress.yaml
```

### admin 비밀번호 확인

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

### cluster 세팅

```
argocd login argocd.smartseo.kr --username admin --password 비밀번호

argocd cluster add 클러스터 arn
```

### DB 배포 예시
