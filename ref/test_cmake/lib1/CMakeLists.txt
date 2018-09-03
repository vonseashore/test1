SET (LIB_SRC lib1.cpp)

# SET (LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)

# three kinds of libraries:
# 1. shared, i.e., dynamic library����̬���ļ���չ����Ϊ "*.so"��
# 2. static, i.e., static library�� ��̬���ļ���չ����Ϊ "*.a";
# ���ң�����ͨ��ϣ����̬��Ͷ�̬���ļ�������һ�£�ֻ����չ����ͬ��
# 3. module, this parameter is valid only when dyld is supported;
# otherwise, will be considered as shared

# ���Ӷ�̬�⣬�ؼ���Ϊshared���㲻��Ҫдȫlibhello.so��
# ֻ��Ҫ��дhello���ɣ�cmakeϵͳ���Զ�Ϊ������ libhello.X
#ADD_LIBRARY (hello SHARED ${LIBHELLO_SRC})

# ���Ӿ�̬�⣬�ؼ���Ϊstatic��
# ADD_LIBRARY (hello STATIC ${LIBHELLO_SRC})
# ��Ȼ��hello��Ϊtarget��ʱ���ǲ��ܳɹ���������ľ�̬��ģ�
# ��Ϊhello��Ϊһ��target�ǲ��������ģ� �ʰ������hello�޸�Ϊhello_static
# ͬ�����㲻��Ҫдȫlibhello_static.a
# ֻ��Ҫ��дhello���ɣ�cmakeϵͳ���Զ�Ϊ������ libhello_static.X
ADD_LIBRARY (lib1 STATIC ${LIB_SRC})


# ����һ���ϰ�ߣ���̬�����ָ���̬������Ӧ����һ�µģ�ֻ����չ����ͬ��
# ������̬����Ϊ libhello.a�� ��̬����Ϊlibhello.so ��
# ���ԣ�ϣ�� "hello_static" �����ʱ������"hello_static"��������"hello"��������ʾ�����������£�
#SET_TARGET_PROPERTIES (hello_static PROPERTIES OUTPUT_NAME "hello")