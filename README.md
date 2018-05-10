# bitvec

```
int nlz32(int x)
{
 int c = 0;
 if (x == 0) return 32;
 if (x & 0xffff0000) { x &= 0xffff0000; c |= 0x10; }
 if (x & 0xff00ff00) { x &= 0xff00ff00; c |= 0x08; }
 if (x & 0xf0f0f0f0) { x &= 0xf0f0f0f0; c |= 0x04; }
 if (x & 0xcccccccc) { x &= 0xcccccccc; c |= 0x02; }
 if (x & 0xaaaaaaaa) { c |= 0x01; }
 return c ^ 31;
}
```
