Instalar ANSIBLE BUILDER:

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.8 get-pip.py
python3.8 -m pip --version
python3.8 -m pip install ansible-builder 


Compilar imagen de contenedor
ansible-builder build --tag ee_oci

Cargar imágen en registry con Podman


  podman login -u ${REGISTRY_NAMESPACE}/${USER} -p "${TOKEN}" ${REGION}.ocir.io
  podman tag localhost/ee_oci:latest iad.ocir.io/${REGISTRY_NAMESPACE}/${REGISTRY}:${TAG}
  podman push ${REGION}.ocir.io/${REGISTRY_NAMESPACE}/${REGISTRY}:${TAG}
