import hashlib

h1 = hashlib.md5()
h1.update('chao_thay'.encode('utf-8'))
int(h1.hexdigest(), 16)
h1.update('chao_thay'.encode('utf-8'))
int(h1.hexdigest(), 16)
int(hashlib.new('md5', ('%s' % 'chao_thay').encode('utf-8')).hexdigest(), 16)
int(hashlib.new('md5', ('%s' % 'chao_thay').encode('utf-8')).hexdigest(), 16)
class BloomFilter():
    def __init__(self, array_size, hash_names):
        self.array_size = array_size
        self.bitarray = [0] * array_size
        self.hash_names = hash_names
        
    def _get_hash_positions(self, value):
        pos = []
        for h in self.hash_names:
            hash_hex = hashlib.new(h, ('%s' % value).encode('utf-8')).hexdigest()
            # convert hashed value into an integer
            asint = int(hash_hex, 16)
            # modulo array_size to fit hash value into the bitarray
            pos.append(asint % self.array_size)
        return pos
        
    def add(self, value):
        hash_pos = self._get_hash_positions(value)
        for pos in hash_pos:
            self.bitarray[pos] = 1
        
    def query(self, value):
        hash_pos = self._get_hash_positions(value)
        for pos in hash_pos:
            if not self.bitarray[pos]:
                return False
        return True
bloom = BloomFilter(array_size=10, hash_names=('md5', 'sha1'))
bloom.bitarray
bloom.add('lam bai nhanh!')
bloom.bitarray
bloom.query('lam bai nhanh!')
bloom.add('Lab 1')
bloom.bitarray
bloom.query('test")
